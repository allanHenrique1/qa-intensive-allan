Título objetivo (ação + falha):
Sistema permite que usuário cadastre caracteres incorretos como nome

Ambiente:
Navegador google chrome

Passos para reproduzir:

1. acessar plataforma
2. adicionar nome
3. adicionar sobrenomme
4. clicar em prosseguir
5. digitar email para ser usado na conta
6. reescrever email que sera usado
7. clicar em proseeguir
8. adicionar em confirmar senha
9. cliclar em cria novo usuário

Resultado esperado:
Que o sistema bloqueie a tentativa de cadastro de usuário com carecteres não permitidos

Resultado atual:
sistema deixa passar e acaba quardadando no banco de dados, dados inconsistentes

*Severidade*:
Alta
*Prioridade*:
Alta

Impacto no usuário ou negócio:
Sistema pode ser prejudicado por guardar informações que estão fora das regras de negocio, acumulando espaço desenecessário no Banco de dados.
