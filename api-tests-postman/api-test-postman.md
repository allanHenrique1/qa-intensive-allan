## Teste de API pública 

usando a api publica do JSONPlaceholder (Uma API pública para fins de estudo), a seguir: Irei dar uma breve explicação sobre o que é uma API, e seguiremos para os exeplos e validações utilizando o postman.

### O que é uma API? 
Vamos pensar num contesto de um restaurante. O  request seria o cliente que pede comida que por sua vez seria o reponse e não muito menos importante o cardápio seria os endpoints, o servidor seria o cozinheiro do restaurante e finalmente a API seira o garço que leva e traz os pedidos.
Vamos imterpretar os verbos HTTP como o humor do garçom: 
200 -> Tudo certo, o pedido foi feito  e entregue
201 -> Digamos que foi uma sugestão de criar um novo intem no cardápio 
404 -> Pedido não foi encontrado
500 -> A conzinha pegou fogo e o garçom veio cheio de fuligem e fumaça lhe dar essa explicação
basicamente essas são intepretações dos principais verbos HTTP.

### Testes e validações:

Consultando a documentação da API para ter acesso aos Endpoints corretos,fiz os sequites testes: 

Teste 001: GET /posts/1

body: 
{
    "userId": 1,
    "id": 1,
    "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
    "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
} 

Status code: 
200 OK 
Estrutura do body: 
Estrutura consisa e bem aplicada
Tipo de dado: 
Ambos os tipos tanto String quanto o int são esperado e estão válidos
Comportamento esperado: 
È esperado que o meu request a API seja bem sucedido com um status code de 200 e
me retorne o conteúdo desejado
E se quebrar em produção?: 
Caso essa request quebre, usuários não poderão acessar os posts desejados


Teste 002: GET /posts/1/comments

body: 
[
    {
        "postId": 1,
        "id": 1,
        "name": "id labore ex et quam laborum",
        "email": "Eliseo@gardner.biz",
        "body": "laudantium enim quasi est quidem magnam voluptate ipsam eos\ntempora quo necessitatibus\ndolor quam autem quasi\nreiciendis et nam sapiente accusantium"
    },
    {
        "postId": 1,
        "id": 2,
        "name": "quo vero reiciendis velit similique earum",
        "email": "Jayne_Kuhic@sydney.com",
        "body": "est natus enim nihil est dolore omnis voluptatem numquam\net omnis occaecati quod ullam at\nvoluptatem error expedita pariatur\nnihil sint nostrum voluptatem reiciendis et"
    },
    {
        "postId": 1,
        "id": 3,
        "name": "odio adipisci rerum aut animi",
        "email": "Nikita@garfield.biz",
        "body": "quia molestiae reprehenderit quasi aspernatur\naut expedita occaecati aliquam eveniet laudantium\nomnis quibusdam delectus saepe quia accusamus maiores nam est\ncum et ducimus et vero voluptates excepturi deleniti ratione"
    },
    {
        "postId": 1,
        "id": 4,
        "name": "alias odio sit",
        "email": "Lew@alysha.tv",
        "body": "non et atque\noccaecati deserunt quas accusantium unde odit nobis qui voluptatem\nquia voluptas consequuntur itaque dolor\net qui rerum deleniti ut occaecati"
    },
    {
        "postId": 1,
        "id": 5,
        "name": "vero eaque aliquid doloribus et culpa",
        "email": "Hayden@althea.biz",
        "body": "harum non quasi et ratione\ntempore iure ex voluptates in ratione\nharum architecto fugit inventore cupiditate\nvoluptates magni quo et"
    }
]

Status code: 
200 OK
Estrutura do body: 
Estrutra ideal para um body, elencando apenas o que foi pedido na request sem erros ou dados vazios e incoerentes
Tipo de dado: 
Todos os dados aparentes nessa response são coerentes e esperados
Comportamento esperado: 
comportamento está totalmente de acordo com o esperado
E se quebrar em produção?: 
Caso quebre, usuário não terão acesso aos comentários dos posts


Teste 003: DELETE /posts/1/

body: 
{} -> vazio

Status code: 
200 ok
Estrutura do body: 
A estrura aparece vazia por conta que foi feita uma deleção do post de ID 1, status code 200 indica o sucesso da operação.
Tipo de dado: 
Sem tipos de dados
Comportamento esperado: 
tudo funcionando perfeitamente
E se quebrar em produção?: 
Caso esse metódo não funcione, como os usuários vão apagar as postagens?


Teste 004: POST  posts/1/

body: 
{} -> vazio

Status code: 
404 Not found
Estrutura do body: 
Vazia pois ocorreu um erro no servidor
Tipo de dado: 
nenhun
Comportamento esperado: 
Comportamento inesperado dectado, era esperado que o usuário fosse capz de conseguir fazer um post e não receber status code 404
E se quebrar em produção?: 
Como nessa caso a response quebrou, os usuários ficam impossibilitados de postar


Teste 005: POST /comments?postId=1

body: 
{
    "id": 501
}

Status code: 
201 Created
Estrutura do body: 
Sem erros, indica que foi criado um novo comentário no post de Id 1
Tipo de dado: 
O dado de tipo INT está coerente e é esperado
Comportamento esperado: 
Comportamento agindo como o esperado nessa situcação de criação de novo post
E se quebrar em produção?: 
Usuários não irão conseguir públicar novos comentários


