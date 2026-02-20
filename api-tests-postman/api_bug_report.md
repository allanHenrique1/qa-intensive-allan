## Bugs de Api
Utulizei o postman junto com a api fake disponibilizada no site fake api real responses, para estudo de api e reporte de bugs. 


Título: API retorna 201 mesmo com dado inválido
Endpoint: https://gorest.co.in/public/v2   /users
Método: POST
Payload enviado: {
    "name": "Luis Henrique",
    "gender": "male",
    "email": "henrique.meireles@15ce.com",
    "status": "unknown"
} 
Status retornado: 201
Resultado esperado: o sistema deve retornar Status 400
Resultado atual: Segundo a documentação oficial, o campo status aceita apenas active ou inactive. Qualquer valor fora desse enum deveria resultar em 422 Unprocessable Entity (ou 400, dependendo da implementação).
Severidade: Alta (afeta controle de acesso)
Prioridade: p1 (não permitir deploy enquanto não for corrigido)


Título: API retorna 500 para erro de usuário
Endpoint: https://gorest.co.in/public/v2   /users/8378251
Método: PATCH
Payload enviado: {
    "name": "Allan Henrique",
    "gender": "unknown",
    "email": "henrique.meireles@15ce.com",
    "status": "active"
} 
Status retornado: 500 
Resultado esperado: Deveria ser retornado status 400
Resultado atual: Ao enviar valor inválido para campo enumerado (gender: unknown), a API retorna 500 Internal Server Error, indicando falha de tratamento de exceção no backend, quando o comportamento esperado seria 422 ou 400.
Severidade: Alta (afeta usabilidade do sistema e acesso ao mesmo)
Prioridade: p1 (deve ser corrigida antes de entrar em deploy e passar por faze de teste)


###Se essa API estiver errada, o que acontece na UI? O banco pode ficar inconsistente? 

1. API aceita status = unknown

2. Banco persiste valor inválido

3. Serviço X consulta WHERE status = 'active'

4. Usuário não aparece

5. Fluxo de ativação quebra

