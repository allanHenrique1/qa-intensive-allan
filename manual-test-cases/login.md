# Neste arquivo vão está listados 10 caso de teste manual usando site The internet 

ID: CT-LOGIN-001
Título: Realizar login com usuário e senha válidos

Pré-condições:
Usuário já cadastrado no sistema
Usuário não está logado
Navegador Google Chrome aberto

Passos:

1. Acessar a página de login do sistema

2. Informar um e-mail válido no campo “E-mail”

3. Informar uma senha válida no campo “Senha”

4. Clicar no botão “Entrar”

Resultado Esperado:

O sistema deve autenticar o usuário
O usuário deve ser redirecionado para a homepage
O nome do usuário deve ser exibido no topo da página

Resultados reais: 
O Usuário foi direcionado para a homepage

Pós-condições:
Aplicativo funciona normalmente

Status: 
Aprovado
 


ID: CT-LOGIN-002
Titulo: Realizar login com senha inválida 

Pré-condições: 
Usuário já cadastrado no sistema 
Usuário não está logado
Usuário digitou senha inválida
Navegador Google Chrome aberto

Passos: 

1. Acessar página de login do sistema 

2. Digitar um email no campo "E-mail"

3. Digitar uma senha no campo "Senha" 

4. Clicar no botão de login 

Resultado esperado: 
O sistema deve exibir mensagem informando o erro no topo da página
O usuário deve ser redirecionado para página de login novamente 

Resultados reais:
Erro foi informado 
Foi solicitado nova tentativa do usuário

Pós-condições:
Aplicativo funciona normalmente

Status:
Aprovado




ID: CT-LOGIN-003
Titulo: Realizar login com e-mail inválida 

Pré-condições: 
Usuário já cadastrado no sistema 
Usuário não está logado
Usuário digitou e-mail inválida
Navegador Google Chrome aberto

Passos: 

1. Acessar página de login do sistema 

2. Digitar um email no campo "E-mail"

3. Digitar uma senha no campo "Senha" 

4. Clicar no botão de login 

Resultado esperado: 
O sistema deve exibir mensagem informando o erro no topo da página
O usuário deve ser redirecionado para página de login novamente 

Condições reais:
Erro foi informado 
Foi solicitado nova tentativa do usuário

Pós-condições:
Aplicativo funciona normalmente 

Status:
Aprovado




ID: CT-LOGIN-004 
Titulo: Login com campos vázios 

Pré-condições: 
Usuário precisa está cadastrado no sistema 
Usuário não está logado
Usuário não digitou nenhum caractere nos campos de login 
Navegador Google Chrome aberto

Passos: 
1. Acessar página de login do sistema

2. Não digitar nenhum carectere no campo "Email"

3. Não digitar nenhum carectere no campo "Senha"

4. Clicar no botão de login 

Resultados esperados: 
Usuário recebe mensagem de erro no canto superior da tela
Usuário não tem acesso a homepage
Será solicitado que o usuário faça login novamente
Navegador Google Chrome aberto

Resultados reais: 
Erro informado, exigindo que o usuário digite seus dados de login
Nova tentativa solicitada

Pós-condições:
site nega entrada e nova tentativa é iniciada
site funciona normalmente

Status:
Aprovado




ID: CT-LOGIN-005
Titulo: Login com senha em braco 

Pré-condições: 
Usuário precisa está cadastrado no sistema 
Usuário não está logado
Usuário não digitou nenhum caractere nos campo de senha
Navegador Google Chrome aberto

Passos: 
1. Acessar página de login do sistema

2. digitar um e-mail no campo "Email"

3. Não digitar nenhum carectere no campo "Senha"

4. Clicar no botão de login 

Resultados esperados: 
Usuário recebe mensagem de erro no canto superior da tela
Usuário não tem acesso a homepage
Será solicitado que o usuário faça login novamente

Resultados reais:
Erro informado, exigindo que o usuário digite seus dados de login
Nova tentativa solicitada

Pós-condições:
site nega entrada e nova tentativa é iniciada
site funciona normalmente

Status:
Aprovado


 

ID: CT-LOGIN-006
Titulo: Login com E-mail em braco 

Pré-condições: 
Usuário precisa está cadastrado no sistema 
Usuário não está logado
Usuário não digitou nenhum caractere nos campo de E-mail
Navegador Google Chrome aberto

Passos: 
1. Acessar página de login do sistema

2. Não digitar nenhum caractere no campo "Email"

3. Digitar uma senha no campo "Senha"

4. Clicar no botão de login 

Resultados esperados: 
Usuário recebe mensagem de erro no canto superior da tela
Usuário não tem acesso a homepage
Será solicitado que o usuário faça login novamente

Resultados reais:
Erro informado, exigindo que o usuário digite seus dados de login
Nova tentativa solicitada

Pós-condições:
site nega entrada e nova tentativa é iniciada
site funciona normalmente

Status:
Aprovado




ID: CT-LOGIN-007
Titulo: Login com caracteres especiais no campo E-mail

Pré-Condições:
Usuário já cadastrado no sistema
Usuário não está logado no sistema 
Usuário digitou carecteres especiais no campo E-mail
Navegador Google Chrome aberto

Passos: 
1. Acessar página de login do sistema

2. Digitar caractere especial no campo "Email"

3. Digitar uma senha no campo "Senha"

4. Clicar no botão de login 

Resultado esperado: 
O sistema devara informar por meio de um indicador que só aceita determinado grupo de caracteres 
O login não será feito no sistema
Usuário será solicitado para digitar o login novamente 

Resultados reais:
Erro informado, exigindo que o usuário digite seus dados de login
Nova tentativa solicitada

Pós-condições:
site nega entrada e nova tentativa é iniciada
site funciona normalmente

Status:
Aprovado



ID: CT-LOGIN-008
Titulo: Login com caracteres especiais no campo senha

Pré-Condições:
Usuário já cadastrado no sistema
Usuário não está logado no sistema 
Usuário digitou carecteres especiais no campo senha
Navegador Google Chrome aberto

Passos: 
1. Acessar página de login do sistema

2. Digitar E-mail no campo "Email"

3. Digitar caracter especial no campo "Senha"

4. Clicar no botão de login 

Resultado esperado: 
O sistema devara informar por meio de um indicador que só aceita determinado grupo de caracteres 
O login não será feito no sistema
Usuário será solicitado para digitar o login novamente 

Resultados reais:
Erro informado, exigindo que o usuário digite seus dados de login
Nova tentativa solicitada

Pós-condições:
site nega entrada e nova tentativa é iniciada
site funciona normalmente

Status:
Aprovado



ID: CT-LOGIN-009
Titulo: Login com caracteres especiais em ambos campos

Pré-Condições:
Usuário já cadastrado no sistema
Usuário não está logado no sistema 
Usuário digitou carecteres especiais no campo email
Usuário digitou carecteres especiais no campo senha
Navegador Google Chrome aberto

Passos: 
1. Acessar página de login do sistema

2. Digitar caracter especial no campo "Email"

3. Digitar caracter especial no campo "Senha"

4. Clicar no botão de login 

Resultado esperado: 
O sistema devara informar por meio de um indicador que só aceita determinado grupo de caracteres nos campos referentes
O login não será feito no sistema
Usuário será solicitado para digitar o login novamente 

Resultados reais:
Erro informado, exigindo que o usuário digite seus dados de login
Nova tentativa solicitada

Pós-condições:
site nega entrada e nova tentativa é iniciada
site funciona normalmente

Status:
Aprovado


ID:CT-LOGIN-010
Titulo: Tentativa falha de login 

Pré-Condições: 
Usuário não esta cadrastado no sistema 
Ter acessado pagina de login 
Navegador chrome aberto

Passos: 
1. Acessar página de login do sistema

2. Digitar email no campo "Email"

3. Digitar senha no campo "Senha"

4. Clicar no botão de login 

Resultados esperados: 
O login será negado 
Ira aparecer um indicador na parte superior da tela indicando o motivo da falha 
Usuário será sugerido que crie sua conta no sistema 

Resultados reais:
Erro informado, sugerindo que o usuário crie novo login
Nova tentativa solicitada

Pós-condições:
site nega entrada e nova tentativa é iniciada
site funciona normalmente

Status:
Aprovado


------CASOS NEGATIVOS------

ID: CTN-LOGIN-001
titulo: Falha na requisição ao back-end

Pré-Condições: 
Usuário pode esta cadatrado na plataforma ou não 
Usuário deve digitar seus dados de login quando solicitado
Acessar pagina de login 
Navegadir Google Chrome aberto

Passos: 
1. Acessar página de acesso a plataforma 
2. Usuário deve digitar seus dados de cadastro como "Email" e "senha" em seus respectivos campos
3. clicar no botão de "Login"

Resultados esperados: 
O botão de "Login" ao ser pressioando e verificado que ouve um erro de comunicação com o backend, irá dispara um popup na tela indicando instabilidades na plataforma 
A página de login sera recarregada manualmente, solcitando reinicio no processo de cadastro

Resultados reais:
Nenhum erro informado pelo sistema
Fica em carregamento 

Pós-condições:
site fica congelado, sem conseguir capturar requisição do backend
site funciona com falhas

Status:
Reprovado


ID: CTN-LOGIN-002
Titulo: Usuário cadastrado tem email ou senha incorretos

Pré-condições: 
Acesso a página de login
Usuário já deve ter conta criada na plataforma
Usuário adicionou dados de login incorretos
Google chrome navegador aberto 

Passos: 
1. Acessar página de login da plataforma 
2. Digitar e inserir dados de login na plataforma
3. Clicar no botão de login 

Resultado esperados: 
Será indicado ao usuário que os seus dados de acesso não estão corretos por meio de um popup
logo após vamos sugerir que ele faça alteração da sua senha e nova tentativar de login será iniciada

Resultados reais:
Erro informado, exigindo que o usuário digite seus dados de login
Nova tentativa solicitada
Susgestão para alteração de senha feita

Pós-condições:
site nega entrada e nova tentativa é iniciada
site funciona normalmente

Status:
Aprovado




ID:CTN-LOGIN-004
Titulo: Falha no envio de requisição do frontend
Pré-condições:
Usuário pode ter conta na plataforma ou não 
Acesso a página de Login
Acesso ao navegador Google Chrome

Passos:
1. Acessar página de login da plataforma 
2. Digitar E-Mail e Senha em seus campos repectivos com "E-Mail" e "Senha"
3. Clicar no botão de "Login"

Resultados esperados:
Backend não ira receber requisição
Não ira retorna com pesquisa se aquele determinado usuário existe no banco de dados da impresa

Resultados reais:
Site permanece estático
Sem resposta ou popup indicando erro ao usuário

Pós-condições
Usuário não saberá o que fazer 
risco em caso de falha será o desconforto e percaussos na usabilidade do cliente
Status:
Reprovado




ID:CTN-LOGIN-005
Titulo: Erro 401 ao acessar página de login

Pré-condições:
Acessar Navegador Google Chrome
Acessar página de login

Passos:
1. Acessar navegador 
2. Tentar acessar página de login

Resultados esperados:
A página devera apresentar erro 401

Resultados reais:
A página apresentou erro 401 
Usuário fica impossibilitado de acessar plataforma

Pós-condições:
Site quebra e não conse ser acessado

Status:
Reprovado


ID:CTN-LOGIN-006
Titulo: Erro de Usuário nâo encontrado
Pré-condições:
Acessar página de login na plataforma
Usuário deve ter conta na plataforma
Acesso ao  google chrome navegador

Passos:
1. Acessar página de login na plataforma
2. Adicionar dados de login nos campos solicitados
3. Clicar no botão de Login

Resultados esperados:
Apresentará popup com indicando que o usuário não foi encontrado
Será sugerido criar novo login

Resultados reais:
A requisição ao banco de dados não consegue encontrar um usuario com aquele email e senha

Pós-condições:
Site sugere que o cliente crie uma nova conta
Site apresenta falhas de requisições
 
Status:
Reprovado



ID:CTN-LOGIN-007
Titulo:Email para recupreção de conta não chega ao usuário
Pré-condições:
Acesso a navegador google chrome
Scesso a pagina de login
Usuario deverá solicitar recuperação de conta

Passos:
1. acesso a pagina de login
2. digitar email no campo email
3. solicitar envio de email para redefinição de senha

Resultados esperados:
O email nunca chega ao cliente 
Não consegue ter acesso a conta com senha antiga

Resultados reais:
cliente fica sem acesso
Pós-condições
site funciona
serviço de mensagem automatica está quebrado
Status:
Reprovado

ID:CTN-LOGIN-008
Titulo: Falha ao cadastrar novo usuário
Pré-condições:
Acesso ao navegador google chrome
acesso a pagina de login
usuário não deve ter conta na plataforma

Passos:
1. acessar plataforma
2. adicionar nome 
3. adicionar sobrenomme
5. clicar em prosseguir
6. digitar email para ser usado na conta
7. reescrever email que sera usado
8. clicar em proseeguir 
9. adicionar em confirmar senha 
10. cliclar em cria novo usuário

Resultados esperados:
usuario recebe notificação indicando que não consegue se cadastrar na plataforma

Resultados reais:
site não funciona corretamente 

Pós-condições
erro ao enviar reiquesição ao banco de dados para criar novo cliente
Status:
reprovado


ID:CTN-LOGIN-009
Titulo:Servidor onde site está hospedado cai repentinamente
Pré-condições:
Acessar navegador google chrome
acessar página de logina

Passos:
1. acessar página de login
2. inserir email e senha 
3. clilcar em login

Resultados esperados:
site cai repetinamente 
apresenta instabilidade no servidor 

Resultados reais:
site funciona normalmente
servidor onde está hosoedado apresenta instabilidades
Pós-condições
servidor apresenta instabilidade recorrente
Risco se falhar será a grande queda de usuários os deixando insatisfeito 
pela instabilidade no sistema e abertura de chamados para resolver o problema
Status:
reprovado

ID:CTN-LOGIN-010
Titulo:Página de acesso com alta demanda
Pré-condições:
acesso ao google chrome
acesso a página de login 
Passos:
1. acessar página de login da plataforma
2. inserir dados de cadastros 
3. clilcar no botão de login

Resultados esperados:
site apresenta grande lentidão 
demora para retornar requisições

Resultados reais:
site apresenta muita instabilidade devido a alta demanda

Pós-condições
clientes ficam sem experiencia fluida na plataforma

Riso se falhar será a grande perca de usuários em horário de pico devido a instabilidade do sistema
Status:
reprovado


