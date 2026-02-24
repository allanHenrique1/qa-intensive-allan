## Consolidação dos estudos para teste E2E 
Aqui irei refinar e aprimorar meus  cenários de fluxo para teste E2E, com 3 cenários especifios. 

## Caso 1 - cadastro válido.
---
 - Objetivo: 
 cadastrar usuário com email válido.

 - Pré-condição:
 Não ter email ativo no sistema

 - Passos: 
 - 1 Após UI enviar o segunite payload:  
{
  "email": "novo.cliente@provedor.com.br",
  "password": "SenhaSegura!2026",
  "password_confirmation": "SenhaSegura!2026",
  "full_name": "Fulano de Tal"
}

- 2 Logo após verificação ser feita no banco de dados, a API "volta" com Status 201, usuário foi criado 
- 3 Em seguida é gerado o token de acesso do usuário: 
{
  "status": "success",
  "message": "Usuário criado com sucesso.",
  "data": {
    "id": 1053,
    "email": "novo.cliente@provedor.com.br",
    "status": "active",
    "created_at": "2026-02-23T12:45:00Z"
  }
}

 - 4 Na tabela users: SELECT * FROM users WHERE id = 1053 deve retornar o regsitro
 - 5 Status: Deve ser criado como "Active" OU ("peding_verification" dependendo da regra de negócio) 
 - 6 Integridade: last_login deve ser NULL (pois ainda não ouve login) 
 
 - Resultado esperado: 
   Sucesso após realizar cadastro do email no sistema
 - Resultado obtido: 
   emial é cadastrado com suceso no sistema 


## Caso 2 – Email duplicado.
---
 - Objetivo: Validar que o sistema não permita cadastro com email já existente
 - Pré-condição: Email já deve existir no sistema

 - Passos 

 - 1 Após usúrio tentar email já castrado, UI é acionda enviando o seguinte payload : 
{
  "email": "usuario.exemplo@provedor.com.br",
  "password": "OutraSenha#123"
}

 - 2 Api pode retonar erro 422 Unprocessable Entity ou 409 Concflict, dependendo contrato uma das duas respostas será retornada 
 - body : 
{
  "error": "registration_failed",
  "message": "Este endereço de e-mail já está em uso.",
  "code": "DUPLICATE_EMAIL"
}


 - 3 Tabela users: O comando SELECT COUNT(*) FROM users antes e depos da requisição deve retornar o mesmo valor. Nenhuma linha nova de ser inserida
 - Integridade: O usuário original com este email, não deve ter nenhum campo(ID,senha ou status) alterado
 
 - Resultado esperado: Novo registro não deve ser criado no sistema.
 - Resultado obtido: Sistema impede de acessar com email já existente no banco de dados


## Caso 3 – Campo obrigatório ausente
---
 - Objetivo: Validar que o sistema cadastre com campos onrigadtórios ausentes no dooby da requisição:
 - Pré-requisito: Email já deve ser existente no sistema
 - Passos: 

  - 1 Payload é enviando com campo obrigatório ausente:
{
  "password": "SenhaSemEmail123"
}

 -  2 A resposta da API esperada será um 400 bad request : 
{
  "error": "validation_error",
  "message": "Campos obrigatórios ausentes.",
  "fields": {
    "email": "O campo e-mail é obrigatório."
  }
}

 - Validação no banco de dados: 
 - 3 Estado: Nenhuma alteração no banco. O banco de dados não deve nem chegar a processar a query, deve travar na camada de aplicação 

 - Resultado esperado: è esperado que API retorne erro 400 de acordo con contrato 
 - Resultado obtido: Api retorna erro 400 bad request
