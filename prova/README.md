# Detecção de Fraudes com SQL

![Credit card fraudster](Images/credit_card_fraudster.jpg)

## Introdução 

A fraude financeira é uma preocupação crescente, e empresas de diversos setores dependem de analistas de dados para identificar padrões de transações incomuns que possam indicar atividades fraudulentas. Neste projeto avançado de SQL, você assumirá o papel de um analista de fraudes e criará um banco de dados para detectar transações suspeitas com cartão de crédito usando dados históricos. Com a ajuda de SQL, você explorará padrões de comportamento, descobrirá anomalias e relatará casos potencialmente fraudulentos, oferecendo valor prático em setores como fintech, bancos e comércio eletrônico.

### Conjunto de dados

Utilize este conjunto de dados de transações com cartão de crédito. Ele inclui dados de transações anonimizados, como valor, data e hora, estabelecimento comercial e rótulos de fraude, perfeito para desenvolver lógica de detecção de fraudes. você deverá simular a construção de um banco de dados transacional utilizando o Databricks. Após a criação e o preenchimento das tabelas com os arquivos CSV's, você terá que utilizar a linguagem SQL para analisar os dados e responder algumas perguntas.

### Modelagem de dados

![QuickDBD-export](Images/QuickDBD-export.png)

### Perguntas de negócio

1. Quais são as 100 maiores transações que ocorreram durante as primeiras horas da manhã (entre 7h e 9h)?

2. Há algum padrão de transações abaixo de US$ 2,00 por titular do cartão que possa indicar cartões clonados?

3. Quais são os 5 principais comerciantes que aparecem com mais frequência em transações suspeitamente pequenas?

4. A CEO do maior cliente da empresa (Titular: Nancy Contreras) suspeita que alguém tenha usado seu cartão de crédito corporativo sem autorização no primeiro trimestre de 2018, para pagar diversas contas caras em restaurantes. Você foi incumbido de encontrar quaisquer transações anômalas durante esse período.

5. Podemos criar views SQL para reutilizar a lógica de detecção de fraudes de forma eficiente?

6. Como as técnicas estatísticas (desvio padrão, intervalo interquartil) podem ajudar a identificar valores anômalos?

### Bônus

Essa parte não é obrigatória, e não valerá ponto, mas fica como desafio para vocês, conforme conversamos no final da última aula, crie um novo catálogo, schema e tabelas através do SQL para simular um ambiente analítico no modelo star schema (fato e dimensões):

![Fato-Dimensao](https://docs.microsoft.com/pt-br/power-bi/guidance/media/star-schema/star-schema-example2.png)

Altere as querys para ter o mesmo resultado que teve no ambiente transacional, veja que a query fica bem mais simples e bem mais performática, visto que o modelo estrela desnormaliza os dados de forma controlada, o que dispensa múltiplos joins em cascata (como no modelo floco de neve).