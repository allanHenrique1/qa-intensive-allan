## Integração de sistema E2E 
Nesse arquivo irei análisar e validar fluxos de teste de ponta a ponta em um sistema de login com 3 casos aparentes.

Caso 1 - Login válido 

 - UI envia o senguinte payload : 
{
  "email": "usuario.exemplo@provedor.com.br",
  "password": "SenhaForte#2026",
  "device_fingerprint": "browser_chrome_windows_10_xyz789",
  "remember_me": true
}  
 
 - Logo após ser enviado a requisição a API retorna Status 200 OK
 - Em seguida o token de acesso é criado consseguentemente criando uma sessão : 
  {
  "status": "success",
  "data": {
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
    "token_type": "Bearer",
    "expires_at": "2026-02-21T16:32:42Z",
    "user": {
      "id": 1052,
      "email": "usuario.exemplo@provedor.com.br",
      "last_login": "2026-02-20T16:32:42Z",
      "status": "active"
    }
  }
}
  
  - Assim que a nova seção é criada o last_login é atualizado com a hora do acesso atual e o token retornado deve existir exatamente na tabela sessions.
  - Nenhuma alteração na senha foi efetuada pelo usuário e nenhum campo inesperado foi modificado.   
  - Tabela users: * O campo last_login deve ser atualizado exatamente para o timestamp retornado na API (2026-02-20T16:32:42Z).
   - O campo password_hash deve permanecer inalterado.
   - O campo status deve permanecer como active.
  - Tabela sessions: * Deve haver um novo registro (INSERT) contendo o user_id: 1052, o token gerado e a data de expiração calculada.
  - Integridade: Nenhum campo adicional (como e-mail ou ID) deve sofrer modificações.






Caso 2 - Senha incorreta

 - Após tentativa de falha acesso do usuário ao sistema o seguinte payload é gerado : 

 {
  "email": "usuario.existente@ecommerce.com.br",
  "password": "SenhaErrada123!"
 }
 
 - Fazendo como que a API retorne de forma esperada o Status 401 Unauthorized, com o seguinte body: 

 {
  "error": "invalid_credentials",
  "message": "E-mail ou senha incorretos."
 }

 - Validação no banco de dados : 
 - Tabela sessions: SELECT COUNT(*) FROM sessions WHERE user_id = {id} deve retornar o mesmo valor de antes da tentativa. Nenhum novo registro deve ser criado.
 - Tabela users: SELECT last_login FROM users WHERE email = '...' deve manter o timestamp da última sessão bem-sucedida. Se houver UPDATE nesta coluna, o sistema apresenta um Bug de Integridade.






Caso 3 - Usuário inativo 

 - Payload de Requisição : 
{
  "email": "usuario.inativo@ecommerce.com.br",
  "password": "SenhaCorretaValida2026"
} 

 - Resposta espera da API: 
 - Status Code : 403 Forbidden 
 - Body da resposta : 
{
  "error": "account_inactive",
  "message": "Acesso negado. Esta conta está desativada ou aguardando confirmação."
}

 - Validação do Banco de dados: 
 - Tabela sessions: Nenhuma linha inserida. O token não deve ser gerado.
 - Tabela users: SELECT status, last_login FROM users WHERE email = '...'.
  - status deve permanecer como inactive (ou similar).
  - last_login deve permanecer nulo ou com a data antiga.
 - Regra de Negócio: A verificação de status deve ocorrer antes ou em conjunto com a validação da senha para evitar processamento desnecessário ou exposição de vetores de ataque.
