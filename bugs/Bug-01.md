🐞 BUG REPORT

Título: Sistema não exibe mensagem clara ao tentar login com usuário não cadastrado

Ambiente:

Sistema: Aplicação Web (Login)
Navegador: Google Chrome
Sistema Operacional: Windows / Linux
Ambiente: Teste (ou Produção, se aplicável)

Passos para reproduzir:

Acessar a página de login do sistema

Informar um e-mail não cadastrado no campo “Email”

Informar qualquer senha válida no campo “Senha”

Clicar no botão “Login”

Resultado Esperado:

O sistema deve negar o login

Deve ser exibida uma mensagem clara informando que o usuário não está cadastrado

O sistema deve sugerir a criação de uma nova conta (ex: link ou botão de cadastro)

Resultado Atual:

O sistema nega o login

Nenhuma mensagem clara é exibida informando que o usuário não possui cadastro

Não há orientação para criação de uma nova conta

Prioridade: Média
Severidade: Média

Impacto:
Usuários não cadastrados não entendem o motivo da falha no login, o que pode gerar abandono do sistema e aumento de chamados de suporte.
