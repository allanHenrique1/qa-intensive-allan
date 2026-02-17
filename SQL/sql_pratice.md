# Estudo de SQL
usei o site SQLBolt como base para meu estudo e revisão de consultas SQL.

## Consultas que um QA usa no dia a dia 

Buscar usuário específico
SELECT * FROM users WHERE Id = 1;

Filtrar usuários ativos
SELECT * FROM users WHERE activit = 'Ativo';

Ordenar por data
SELECT * FROM users ORDER BY data_criacao; 

Contar registros
SELECT COUNT(*) FROM users;

Buscar por parte do nome (LIKE)
SELCT * FROM users WHERE nome LIKE 'Al%';

Validar Update/deleção
SELECT * FROM users; 

Saber se usuário foi cadatrado no sistema
SELECT * FROM users WHERE name = 'Allan';

Investigar inconsistências e investigar situações críticas
SELECT * FROM users WHERE name = 'Allan' AND id = 1;

Investigar registros parecidos 
SELECT * FROM users WHERE email = '@gmail.com';

## Como SQL ajuda o QA a provar bugs? 
Um QA trabalha como uma especie de detetive que investiga inconsistencias e falhas que podem gerar defeitos na aplicação, e desse modo gerar um produto defeituoso para o cliente. Como todo bom detetive tem uma lupa, o QA não pode deixar de ter a sua o SQL (Structured Query Language) funciona como uma especie de lupa no banco de dados que investiga e mais imoprtante consegue provar onde está a inconsistencia, para desse modo acionar os devs para efetuar a devida correção.



