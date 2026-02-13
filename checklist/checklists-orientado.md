## Checklist de testes orientado a risco
Esse arquivo contém testes orientado a risco o qual o foco principal é desenvolver 
a mentalidade de um QA analista e que é responsável pelo protudo.

Sistema onde funcionários de uma farmácia batem seu ponto diariamente matem a gestão de vendas.

Área / funcionalidade
Registro de horas extra por funcionário
O que pode dar errado
Sistema não salvando quantidade de horas em seu BD
Impacto se der errado
Usuários irão ficar insatisfeitos, não poderá ser efetuado o pagamento p/ hora extre sem esses dados
Precisa testar sempre? (sim/não)
sim, pois é uma funcionalidade critica do sistema


Área / funcionalidade
Atribuir vendas a um vendedor
O que pode dar errado
Sistema atrubuir vendas de um vedendor X para Y 
Impacto se der errado
Isso daria um problema absurdo no RH da empresa na hora de calcular bonificações por venda
Precisa testar sempre? (sim/não)
Sim, funcionalidade extremamente critica


Área / funcionalidade
Exibir mensagem de erro
O que pode dar errado
Menssagem de erro mal formatada 
Impacto se der errado
Farmaceutico pode ter interpretação mal induzida pelo erro, causado ruidos na usabilidade
Precisa testar sempre? (sim/não)
Não é critico, apenas um correção basta
