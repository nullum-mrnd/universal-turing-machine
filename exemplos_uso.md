## Exemplos de Uso para a MTU criada ##

# Introdução

O input da MTU (máquina de Turing universal) receberá uma entrada codificada que contém transições de uma MT e uma palavra, decidindo se ela é aceita ou não.
Sobre a entrada codificada, as transições são definidas como:

`<q(estado_origem)><a(simbolo_lido)><a(simbolo_escrito)><direcao(L/R)><q(estado_destino)>`

É possível receber mais de uma transição e elas são separadas por <#>.
As entradas surgem após a definição de transição, iniciando a partir do caractere <$>

Exemplo de input: `q1a1a1Rq1#q1a11a1Lqf$a1a11`

# Casos de aceite

- Corretos:

`q1a1111a11Rqf$a1111`

`q1a1a11Rq11#q11a11a111Lqf#q11a1a11Rq1$a1a11`

`q1a1a1Rqf#q1a11a11Rqf#q1a111a111Rqf$a1a111a11`

`q1a1a1Rq111111111#q111111111a1a11111Rq11111111#q11111111a11111a111Rq1111111#q1111111a111a1111Rq11#q11a1111a1111111Rq1111#q1111a1111111a1111111111Rqf$a1a1a11111a111a1111a1111111a1111111111`

- Rejeitados: 

`bbq1a1111a11Rqf$ba1111b`

`bb1q11a1a11Rqf$a1a1a1`

`q1a1a1Rqf$ba1a1a1`

`q1a1a1Rq111111111#q111111111a1a11111Rq11111111#q11111111a11111a111Rq1111111#q1111a1111111a1111111111Rqf$a11a1a111`

# Casos de não aceitamento

- Rejeitados

`q1a1a11Rq11#q1a1a1Rqf$11a1a1a1`

`q1a1a111Rq11q11a11a111Lqf$a1a1a11`

`q1a1a1RLa111Lqf$a1ba1111`

`q1a1a1La111a1111Lqf$a1a111`
