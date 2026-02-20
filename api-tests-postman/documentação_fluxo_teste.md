## Docunentação par fluxo de teste em APIs 

Api da GoRest foi utilizada para fins de estudo. 

🔹 Fluxo 1 — Criação e Consulta

1. Criar usuário (POST)

2. Confirmar retorno 201

3. Pegar ID retornado

4. Buscar usuário com GET

5. Validar todos os campos

6. Conferir consistência

Pergunta crítica:
O que acontece se eu tentar criar dois usuários com o mesmo email? 
A API informa que já existe um usuário ativo com aquele email

Documentação do Fluxo 1 

Objetivo do teste
Validar fluxo completo de criação e persistência de usuário garantindo conformidade com contrado da API dos dados retornados
Pré-condição
Usuário deve ser inexistente na API
Passos
1. Passar todos os dados previstos na documentação da API no body
2. Fazer requisição POST na URL da API 
3. Verirfcar se API retorna Status 201

Resultado esperado
Retorna 201 com ID que seja único, persistencia de dados corretamente repeitando o contrato da API, tento em vista o payload que foi enviado : Payload enviado: {
    "name": "Luis Henrique", "gender": "male","email": "henrique.meireles@15ce.com",
    "status": "active"}, foram validados os campo de : name, email,gender,status comparando campo por campo e validando os tipos de dados enviados no payload após comparando os IDs do response do GET e do POST que era os mesmos. 
Resultado atual
Usuário é criado com sucesso.Status 201 retornado, ID único gerado,dados retornados noGET idênticos ao payload enviado.
Status (Pass/Fail)
PASS
Observações técnicas
Para melhor manuseio da API é necessário leitura prévia da API






🔹 Fluxo 2 — Atualização

1. Criar usuário

2. Atualizar campo válido (PATCH)

3. Validar persistência

4. Atualizar campo inválido

5. Validar tratamento de erro

Pergunta crítica:
A API mantém padrão de status code?
O PATCH válido retorna status 200, já os inválidos retornam 422 sendo adotado esse padrão de tratamento no contrato da API Extinguindo todas as inconsistencias provenientes que poderiam existir entre o POST e PATCH.

Documentação do Fluxo 2: 

Objetivo do teste
Atualizar cadastro de usuário
Pré-condição
Deve existir um usuário para atualização ser concluida 
Passos
1. estar com acesso ao Postam 
2. Ter usuário criado 
3. Fazer uma requisição PATCH a URL da API
4. Passar campos válidos que desejam ser alterados no body 
5. verificar se alterações foram feitas
Resultado esperado
Que dados do usuário sejam atualizados
Resultado atual
Dados do usuário são atualizados com sucesso.
Status (Pass/Fail)
Pass
Observações técnicas
Vale salientar que deve-se verificar se os dados que devem ser atualizados sejam permitidos pela API.







🔹 Fluxo 3 — Exclusão

1. Criar usuário

2. Deletar usuário

3. Tentar buscar novamente

4. Validar 404

Pergunta crítica:
O delete realmente remove ou apenas desativa?
Usuário é realmente deletado, conseguimos provar isso após um GET buscando por aquele Id espécifico do usuário.
 
Documentação do Fluxo 3: 

Objetivo do teste
Deletar usuário permanentemente
Pré-condição
Ter um usuário cadastrado na API
Passos
1. Ter usuário criado 
2. Fazer requisiçãoo DELETE na API e passar Id usuário desejado na requisição
3. Fazer uma requisição GET a URL da API, buscando pelo ID do user (verificar se deleção foi realmente executada)

Resultado esperado
Usuário seja deletado e não desativado do sistema
Resultado atual
Após efetuar a requisição para deleção do usuário o status retornado é de 204, sem a existencia de um soft delete uma vez que atraves de um GET buscando pelo Id do usuário deletado não é possivel mais buscar encontra-lo. Id não vai ser reutilizado caso seja necessario efetuar um POST para testar isso, pode ser utilizado os mesmo dados anterios para criar nova conta, desse modo provado que o usuário foi apagado corretamente.
Status (Pass/Fail)
Pass
Observações técnicas
Sempre verificar o Id do usuário corretamente antes de efetuar a requisição
