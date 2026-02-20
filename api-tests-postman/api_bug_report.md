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
Resultado atual: API está deixando usuários serem registrados com dados inválidos 
Impacto: Usuário é cadsatrado com "Status" desconhecido, com isso vai acarretar erros na usabilidade do sistema pois alguns recuross foram projetados para funcionar apenas para usuários com conta ativa.
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
Resultado atual: é retornado um erro 500
Impacto: Um erro 500 indica geralmente erro no servidor e não na requisição do cliente, esse falha no tranamento de dados acarreta grande baixa na demada do serviço visto que usuário será impedido de acessar após erro 500
Severidade:Alta (afeta usabilidade do sistema e acesso ao mesmo)
Prioridade: p1 (deve ser corrigida antes de entrar em deploy e passar por faze de teste)




Título: API retorna informação sensível
Endpoint: https://gorest.co.in/public/v2/users/8378251
Método: GET
Payload enviado: apenas é necessário passar url e serviço desejados
Status retornado: 200
Resultado esperado: é esperado que esse tipo de dado sensível não seja tão esposto assim
Resultado atual: dados sensiveis são espostos livrimente, colocando a segurança em constante ameaça
Impacto: Sistema fica absurdademente sensivel e sucetivel a ataques, esposição de dados, invasões hackers e coisas do genero, a segurança a integridade de dados está em cheque
Severidade: Alta (Dados estãp altamente vulneráveis
Prioridade: p1 (Não deveria ter subido isso em produção, testes rigorosos devem ser feito antes de uma atualização entrar de deploy)


###Se essa API estiver errada, o que acontece na UI? O banco pode ficar inconsistente? 

Na UI não serão tão perceptiveis em sinais de falhas na api, enventualmente um botão não será acionado corretamente por falha de requisição, mas o banco de dados em si pode receber vários dados inconsistentes e que não deveriam estar lá, seja por erro de regras de negocio ou eventuais falhas no sistema, desse modo gerando um sistema falho inconsistene e ruim de escalar.


