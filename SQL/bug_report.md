## Transformando Bug validation em bug report  

Título:
Boleto agendado pago apenas com atraso 
Ambiente:
App instalado em dispositivo Android 15
Passos:
1. Abrir app do banco 
2. Acessar aba de agendamentos
3. Selecionar agendamento de boleto 
4. Designar data para pagamento 
5. Confirmar data

Resultado esperado:
Pagar boleto na data escolhida
Resultado atual:
Pago apenas um dia após o que foi escolhido 
Evidência SQL:
SELECT * FROM users ORDER BY data_criacao_boleto;
Impacto no negócio:
Insatisfação ṕor parte dos usuários, falha na integriade e legitimidade dos dados
Severidade:
Alta
Prioridade:
Alta
