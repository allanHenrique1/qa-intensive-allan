## Validação de bugs com SQL 
Nesse arquivo irei documentar meu estudo com base em 3 cenários de bugs baseados em dados e ao final irei escolher um e fazer um bug report detalhado. 

Cenário 1 - usuário com permissão negada

Contexto: 
Usuário aparece como "negado" na UI da empresa
Query usada: 
SELECT * FROM users WHERE permission = 'permitido';
Resultado no banco: 
Ativo
Incosistẽncia encontrada: 
UI mostra negado, banco mostra permitido
Impacto: 
Sistema está bloqueando usuário que deveria ter permissão

Cenário 2 - Boleto pago automaticamente 

Contexto: 
Boleto pago automaticamente somente após a data que o usuário indicou
Query usada: 
SELECT * FROM users ORDER BY data_criacao_boleto;
Resultado no banco: 
18/02/2026 quando deveria ser mostrado 17/02/2026, está sendo acrescentado +1 dia
Incosistẽncia encontrada: 
Banco indica inconsistẽncia ou falha de projeção 
Impacto:
dados inconsistentes, risco financeiro

Cenário 3 - Deletar professor de sistema escolar

Contexto: 
UI indica que professor não foi removido do sistema após deleção
Query usada: 
SELECT * FROM professores;
Resultado no banco: 
Registro ausente
Incosistẽncia encontrada: 
UI com inconsistencia em requisição e obter respsta do banco 
Impacto: 
falha de integridade
