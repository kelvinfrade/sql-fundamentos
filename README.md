## **Introdução**

Bem-vindos ao nosso treinamento de SQL no **Databricks**. Hoje, vamos explorar os conceitos básicos de bancos de dados e como o Databricks pode ser usado para gerenciar e analisar dados de forma eficiente e escalável. 

Nesta aula, exploraremos como usar comandos SQL no Databricks para resolver desafios reais de negócios. Vamos entender como manipular dados em grande escala e como essas ferramentas podem gerar insights estratégicos para diferentes áreas da organização. O foco será em comandos essenciais, como **SELECT**, **JOIN**, **GROUP BY**, **HAVING**, e técnicas avançadas como **Subqueries**, **CTEs**, **Views**, e **Criação de Tabelas**.

Link do excel: https://docs.google.com/spreadsheets/d/1ebChXrvERo9ohuwG4DF6TL4lkrEX8j2Si0q3rkuRNHo/edit?usp=sharing

---

## **Comandos SQL Abordados**

### **Comandos Essenciais**
1. **SELECT:** Para consultar dados de tabelas.
2. **FROM:** Para definir a origem dos dados.
3. **WHERE:** Para aplicar filtros.
4. **GROUP BY e HAVING:** Para agrupar e filtrar dados agregados.
5. **ORDER BY:** Para ordenar os resultados.
6. **LIMIT:** Para restringir o número de linhas no resultado.
7. **JOINs:** Para combinar dados de tabelas relacionadas (**INNER JOIN**, **LEFT JOIN**, **RIGHT JOIN**).
8. **Subqueries:** Para consultas aninhadas e cálculos dinâmicos.
9. **CTEs:** Para organizar e simplificar consultas complexas.
10. **Views:** Para criar tabelas virtuais baseadas em consultas.
11. **Criação de Tabelas:** Para armazenar resultados de análises de forma permanente.

---

## **Desafios de Negócio**

### **Desafio 1: Produtos Mais Vendidos**
**Objetivo:** Identificar os produtos mais vendidos por quantidade para otimizar estratégias de estoque e marketing..

### **Desafio 2: Clientes Mais Lucrativos**
**Objetivo:** Determinar os clientes que mais geraram receita para a empresa.
---

## **Objetivos da Aula**

Ao final desta aula, você será capaz de:
1. Entender como cada comando SQL se aplica a cenários reais.
2. Resolver desafios de negócios utilizando SQL no Databricks.
3. Explorar e manipular dados de forma eficiente para gerar insights acionáveis.
4. Compreender como o SQL pode ser usado para trabalhar com grandes volumes de dados no Databricks.

---

## **Por que Databricks?**

O **Databricks** é uma plataforma unificada de análise de dados que combina o poder do **Apache Spark** com ferramentas avançadas para manipulação de dados em grande escala. Ele se destaca por:

- **Escalabilidade:** Trabalha com dados estruturados e não estruturados em larga escala.
- **Delta Lake:** Uma camada de armazenamento que suporta **ACID transactions**, **versioning** e **time travel**.
- **Integração:** Fácil conexão com diversos serviços de nuvem, como AWS, Azure e Google Cloud.
- **Colaboração:** Notebooks interativos que permitem equipes colaborarem em tempo real.

Além disso, o Databricks facilita o aprendizado e prática com SQL, Python e outras linguagens de análise e engenharia de dados.

---

## **Informações Adicionais**

Aqui estão alguns recursos para complementar seus estudos:

- **Documentação Oficial:**  
  [Databricks SQL Documentation](https://docs.databricks.com/sql/index.html)  
  Toda a referência técnica sobre o uso do SQL no Databricks.

- **Comunidade:**  
  [Databricks Community Edition](https://community.databricks.com/)  
  Participe da comunidade e use a versão gratuita do Databricks para praticar.

---

## Diferença Entre Excel e Databricks

Embora ambos sejam usados para manipular dados, o Excel e o Databricks têm conceitos e finalidades diferentes. A tabela a seguir ilustra essas diferenças:

| **Aspecto**         | **Excel**                             | **Databricks**                          |
|----------------------|---------------------------------------|------------------------------------------|
| **Armazenamento**    | Arquivos locais (XLSX, CSV)           | Bancos de dados e Data Lakes na nuvem    |
| **Tamanho dos Dados**| Limitado (cerca de 1 milhão de linhas)| Virtualmente ilimitado                   |
| **Colaboração**      | Individual ou em rede limitada        | Colaboração em tempo real na nuvem       |
| **Processamento**    | Local no computador do usuário        | Distribuído em clusters (nós e workers)  |
| **Interface**        | Visual e baseada em planilhas         | Baseada em notebooks e queries SQL       |
| **Automação**        | Suporte a macros e VBA                | Totalmente programável (Python, SQL, etc.) |
| **Finalidade**       | Análises locais e rápidas             | Análises escaláveis e aprendizado de máquina |

---

## Comparação de Estruturas: Database vs Excel

No Excel, os dados são armazenados e organizados em **planilhas** (worksheets), enquanto no Databricks os dados estão em **bancos de dados** (databases) e **tabelas**. Vamos entender essa diferença:

| **Conceito no Excel** | **Conceito no Databricks** | **Descrição**                                                                                     |
|------------------------|---------------------------|---------------------------------------------------------------------------------------------------|
| Planilha               | Tabela                   | Uma tabela no Databricks é como uma planilha no Excel: contém linhas e colunas.                  |
| Abas                   | Tabelas em um Database   | No Databricks, várias tabelas são armazenadas dentro de um banco de dados.                       |
| Fórmulas               | Queries SQL              | No Databricks, usamos SQL para manipular os dados em vez de fórmulas predefinidas do Excel.      |
| Power Query            | Transformações com SQL   | A funcionalidade de Power Query do Excel é similar às transformações que podemos realizar no Databricks com SQL. |

---

## Arquitetura Cliente-Servidor: Databricks vs Excel

O **Excel** e o **Databricks** têm arquiteturas distintas:

### **Excel: Arquitetura Local**
No Excel, tudo acontece no seu computador:
- O software é instalado localmente.
- Os cálculos e o processamento ocorrem no hardware do usuário.
- As limitações são impostas pela capacidade do computador (memória, CPU, etc.).
  
Essa abordagem é excelente para pequenas análises, mas torna-se inviável para grandes volumes de dados.

---

### **Databricks: Arquitetura Cliente-Servidor**

O Databricks utiliza uma arquitetura distribuída e baseada em nuvem. Aqui estão os principais componentes:

1. **Cliente**:
   - A interface web onde você escreve consultas SQL, cria notebooks ou visualiza resultados.
   - Não é responsável pelo processamento, mas apenas por enviar as instruções ao servidor.

2. **Servidor**:
   - O Databricks processa os dados usando o Apache Spark em um ambiente distribuído.
   - Isso significa que os dados são divididos em blocos e processados simultaneamente por múltiplos workers.

---

### Diferenças Práticas

| **Aspecto**               | **Excel (Local)**                  | **Databricks (Distribuído)**                              |
|----------------------------|------------------------------------|----------------------------------------------------------|
| **Processamento**          | No computador do usuário           | Em clusters distribuídos na nuvem                        |
| **Escalabilidade**         | Limitada à capacidade do hardware  | Altamente escalável, dependendo do número de nós         |
| **Velocidade**             | Reduzida para grandes volumes      | Processamento paralelo acelera a análise                |
| **Colaboração**            | Difícil em arquivos compartilhados | Simultânea, com usuários trabalhando no mesmo cluster    |

---

## Como o Databricks Transforma a Análise de Dados

Se você já domina Excel, imagine uma planilha sem limites de linhas ou colunas, onde:
- Você pode realizar cálculos complexos sem preocupar-se com a performance do seu computador.
- É possível conectar-se diretamente a fontes de dados na nuvem.
- As análises podem ser feitas de forma colaborativa e escalável.

O Databricks permite que você execute essas tarefas e muito mais.

### Exemplo Prático de Escalabilidade:
No Excel, abrir um arquivo com 2 milhões de linhas pode travar o computador. No Databricks:
1. Você pode carregar esses dados em uma tabela sem problemas.
2. Consultar apenas os dados necessários usando SQL.
3. Realizar análises em segundos, independentemente do volume.

---

## **Preparando o Ambiente**

### **1. Criar Conta no Databricks Community Edition**
O primeiro passo é configurar sua conta gratuita no Databricks Community Edition. Este ambiente permitirá que você experimente as funcionalidades do Databricks sem custo algum.

1. Acesse o site: [Databricks Community Edition](https://community.databricks.com/).
2. Registre-se usando um e-mail válido.
3. Configure o ambiente, criando um **cluster** para executar os notebooks.

---

Vou criar uma aula única e detalhada, abordando todos os tópicos mencionados com exemplos de código, explicações completas e paralelos com o Excel. Aqui está a aula:

---

# Aula: Comandos SQL em Detalhes no Databricks

Nesta aula, exploraremos em profundidade os principais comandos SQL utilizados para consultas e manipulação de dados no Databricks. Nosso objetivo é garantir que você compreenda como cada comando funciona, suas aplicações e como eles se relacionam com o uso no Excel, um software amplamente utilizado para análises de dados.

---

## Introdução ao Dataset

Utilizaremos o dataset que criamos anteriormente, contendo três tabelas principais:

- **`vendas`**: Informações sobre transações de vendas.
- **`clientes`**: Dados dos clientes.
- **`produtos`**: Detalhes sobre os produtos vendidos.

Antes de iniciar, vamos revisar as primeiras linhas dessas tabelas para relembrar seus conteúdos.

```sql
SELECT * FROM vendas LIMIT 10;
SELECT * FROM clientes LIMIT 10;
SELECT * FROM produtos LIMIT 10;
```

---

# Guia Completo de Comandos SQL no Databricks

Este guia detalhado aborda os comandos SQL mais importantes, desde os mais básicos, como **SELECT**, até os mais avançados, como **JOIN** e **CTE**. A proposta é explicar cada comando com exemplos práticos, paralelos com Excel e dicas para uso no Databricks. Vamos explorar tudo o que você precisa saber para dominar consultas SQL.

---

# Guia Detalhado de Comandos SQL com Contexto de Negócio

Este guia detalhado explora os comandos SQL mais usados, abordando como aplicá-los em cenários reais de negócios. A proposta é fornecer não apenas exemplos de uso técnico, mas também o contexto em que cada comando pode ser útil para análises estratégicas e operacionais.

---

## **1. SELECT** – **O Ponto de Partida**

O comando **SELECT** é usado para recuperar dados de uma ou mais tabelas, sendo essencial para começar qualquer consulta.

### **Por que usar?**
Você quer visualizar dados brutos ou criar relatórios baseados em colunas específicas. Isso é útil, por exemplo, para extrair informações de vendas, produtos ou clientes.

### **Exemplo de Negócio:**
Você precisa verificar o preço e o nome de todos os produtos disponíveis para otimizar sua estratégia de precificação.

#### Exemplo 1: Selecionar todas as colunas
```sql
SELECT * FROM produtos;
```
**Contexto de Negócio:** Visualize todos os detalhes de produtos, como ID, nome, categoria e preço unitário. Isso é útil para uma revisão geral ou para verificar a integridade do banco de dados.

#### Exemplo 2: Selecionar colunas específicas
```sql
SELECT id_produto, nome_produto, preco_unitario FROM produtos;
```
**Contexto de Negócio:** Exiba apenas as informações relevantes, como o nome e o preço dos produtos, ignorando detalhes como estoque ou categoria.

---

## **2. FROM** – **De Onde os Dados Vêm**

O comando **FROM** define a origem dos dados. Toda consulta começa referenciando uma tabela ou um conjunto de tabelas.

### **Por que usar?**
Sem o **FROM**, o SQL não sabe de onde buscar os dados. Pense nele como escolher uma planilha específica no Excel.

#### Exemplo: Selecionar dados da tabela `produtos`
```sql
SELECT * FROM produtos;
```
**Contexto de Negócio:** Analisar os dados completos de uma tabela, como produtos ou clientes, antes de iniciar uma análise detalhada.

---

## **3. COUNT** – **Quantificar os Dados**

O comando **COUNT** é usado para contar o número de linhas em um conjunto de dados ou resultado de consulta.

### **Por que usar?**
Você quer entender o volume de dados, como a quantidade de vendas realizadas, clientes cadastrados ou produtos disponíveis.

#### Exemplo 1: Contar o total de produtos cadastrados
```sql
SELECT COUNT(*) AS total_produtos FROM produtos;
```
**Contexto de Negócio:** Determine quantos produtos você tem em seu portfólio para avaliar a diversidade da oferta.

---

## **4. DISTINCT** – **Removendo Duplicatas**

O comando **DISTINCT** retorna valores únicos em uma ou mais colunas, ajudando a evitar duplicatas nos resultados.

### **Por que usar?**
Quando você precisa identificar elementos únicos, como categorias de produtos, cidades de clientes ou métodos de pagamento.

#### Exemplo 1: Listar todas as categorias de produtos
```sql
SELECT DISTINCT categoria FROM produtos;
```
**Contexto de Negócio:** Veja todas as categorias de produtos para avaliar a segmentação do portfólio.

#### Exemplo 2: Listar combinações únicas de categoria e preço
```sql
SELECT DISTINCT categoria, preco_unitario FROM produtos;
```
**Contexto de Negócio:** Analise como os preços estão distribuídos por categoria.

---

## **5. WHERE** – **Filtrando os Dados**

A cláusula **WHERE** é usada para filtrar registros com base em condições específicas.

### **Por que usar?**
Para buscar dados que atendam a critérios específicos, como produtos acima de um certo preço ou vendas em uma determinada data.

#### Exemplo 1: Produtos com preço maior que R$100
```sql
SELECT * FROM produtos WHERE preco_unitario > 100;
```
**Contexto de Negócio:** Identifique produtos premium para estratégias de marketing focadas em alta margem.

#### Exemplo 2: Produtos da categoria "Eletrônicos"
```sql
SELECT * FROM produtos WHERE categoria = 'Eletrônicos';
```
**Contexto de Negócio:** Analise produtos eletrônicos para planejar promoções sazonais.

#### Exemplo 3: Contar produtos de uma categoria específica
```sql
SELECT COUNT(*) AS total_eletronicos FROM produtos WHERE categoria = 'Eletrônicos';
```
**Contexto de Negócio:** Identifique o número de produtos na categoria "Eletrônicos" para entender o tamanho desse segmento.

---

## **6. LIMIT** – **Restringindo o Volume de Dados**

O **LIMIT** restringe o número de linhas retornadas pela consulta, ajudando a focar em uma amostra específica.

### **Por que usar?**
Para reduzir o volume de dados analisados inicialmente ou criar relatórios com os principais resultados.

#### Exemplo: Selecionar os 5
```sql
SELECT * FROM produtos LIMIT 5;
```
**Contexto de Negócio:** Identifique 5 produtos.

---

## **7. ORDER BY** – **Organizando os Resultados**

A cláusula **ORDER BY** organiza os resultados com base em uma ou mais colunas.

### **Por que usar?**
Para visualizar os dados de forma ordenada, facilitando a identificação de padrões, como produtos mais baratos ou clientes mais ativos.

#### Exemplo 1: Ordenar produtos por preço (crescente)
```sql
SELECT * FROM produtos ORDER BY preco_unitario ASC;
```
**Contexto de Negócio:** Identifique produtos mais acessíveis para estratégias de vendas baseadas em preço.

#### Exemplo 2: Ordenar produtos por categoria e preço (decrescente)
```sql
SELECT * FROM produtos ORDER BY categoria, preco_unitario DESC;
```
**Contexto de Negócio:** Analise os preços dentro de cada categoria para identificar padrões ou anomalias.

#### Exemplo 3: Selecionar os 5 produtos mais caros
```sql
SELECT * FROM produtos ORDER BY preco_unitario DESC LIMIT 5;
```
**Contexto de Negócio:** Identifique os produtos de maior valor para campanhas exclusivas ou análises de rentabilidade.

---

## **8. MIN, MAX, SUM, AVG** – **Resumo de Dados Numéricos**

Essas funções agregadas ajudam a calcular estatísticas como o menor valor, maior valor, soma e média.

### **Por que usar?**
Para obter uma visão consolidada dos dados numéricos, como preço médio, valor total vendido ou produto mais caro.

#### Exemplo 1: Menor e maior preço de produtos
```sql
SELECT MIN(preco_unitario) AS menor_preco, MAX(preco_unitario) AS maior_preco FROM produtos;
```
**Contexto de Negócio:** Avalie a amplitude de preços no portfólio.

#### Exemplo 2: Soma e média dos preços de produtos
```sql
SELECT SUM(preco_unitario) AS soma_precos, AVG(preco_unitario) AS media_precos FROM produtos;
```
**Contexto de Negócio:** Entenda o valor médio e total dos produtos disponíveis.

---

## **9. GROUP BY** – **Agrupando Dados**

O **GROUP BY** agrupa registros para aplicar funções agregadas.

### **Por que usar?**
Para criar relatórios baseados em categorias ou segmentos, como vendas por cidade ou preços médios por categoria.

#### Exemplo: Preço médio por categoria
```sql
SELECT categoria, AVG(preco_unitario) AS media_precos FROM produtos GROUP BY categoria;
```
**Contexto de Negócio:** Compare categorias de produtos com base em seu preço médio.

---

## **10. HAVING** – **Filtrando Grupos**

A cláusula **HAVING** filtra grupos criados com **GROUP BY**.

### **Por que usar?**
Quando você precisa aplicar filtros após a agregação dos dados.

#### Exemplo: Categorias com preço médio acima de R$100
```sql
SELECT categoria, AVG(preco_unitario) AS media_precos
FROM produtos
GROUP BY categoria
HAVING AVG(preco_unitario) > 100;
```
**Contexto de Negócio:** Foco em categorias premium para estratégias de alta margem.

---

## **11. JOIN** – **Combinando Tabelas**

Os **JOINs** são uma das partes mais importantes do SQL, usados para combinar dados de duas ou mais tabelas. Isso é essencial em bancos de dados relacionais, onde as informações estão distribuídas em várias tabelas. Este guia detalha os diferentes tipos de JOIN, com explicações práticas, comparações com Excel e exemplos.

---

## **Módulo de JOIN: INNER, LEFT e RIGHT**

Os comandos de **JOIN** são essenciais para combinar tabelas em SQL. Eles permitem unir informações de diferentes tabelas com base em uma relação lógica, geralmente definida por uma chave comum, como `id_produto`.

### **1. O que é JOIN?**

**JOIN** conecta duas ou mais tabelas e retorna dados combinados. Dependendo do tipo de JOIN, podemos incluir:
- Somente os registros que têm correspondência em ambas as tabelas (**INNER JOIN**).
- Todos os registros de uma tabela, mesmo sem correspondência na outra (**LEFT JOIN** ou **RIGHT JOIN**).

---

### **Comparação com Excel**

No Excel, **JOIN** equivale a:
- **INNER JOIN**: Funciona como **PROCV**, retornando apenas os registros que têm correspondência.
- **LEFT JOIN**: Similar ao **PROCV**, mas mantém os valores da tabela base, mesmo que não haja correspondência.
- **RIGHT JOIN**: Invertido, mantendo todos os valores da tabela pesquisada, mesmo sem correspondência.

---

## **2. Tipos de JOIN e Casos de Negócio**

A seguir, veremos **INNER JOIN**, **LEFT JOIN** e **RIGHT JOIN**, com exemplos de negócio detalhados.

---

### **INNER JOIN: Produtos Vendidos e Total de Vendas**

O **INNER JOIN** retorna apenas os registros que têm correspondência em ambas as tabelas. 

#### **Caso de Negócio: Total de Vendas por Produto Vendido**

Queremos calcular o total de vendas (em valor) por produto. Isso ajuda a identificar os produtos mais vendidos.

#### **Exemplo de Dados**

**Tabela Produtos (`produtos`):**
| id_produto | nome_produto        | categoria       | preco_unitario |
|------------|---------------------|-----------------|----------------|
| 1          | Notebook Ultra      | Eletrônicos     | 3000.00        |
| 2          | Smartphone Pro      | Eletrônicos     | 2000.00        |
| 3          | Mesa Compacta       | Móveis          | 500.00         |

**Tabela Vendas (`vendas`):**
| id_venda | id_produto | quantidade | data_venda  |
|----------|------------|------------|-------------|
| 1        | 1          | 2          | 2023-01-01  |
| 2        | 2          | 1          | 2023-01-02  |
| 3        | 3          | 5          | 2023-01-03  |

#### **Query**
```sql
SELECT 
    p.id_produto, 
    p.nome_produto, 
    SUM(v.quantidade * p.preco_unitario) AS total_vendas
FROM vendas v
INNER JOIN produtos p ON v.id_produto = p.id_produto
GROUP BY p.id_produto, p.nome_produto
ORDER BY total_vendas DESC;
```

#### **Explicação**
- **INNER JOIN**: Conecta as tabelas `vendas` e `produtos` com base no `id_produto`.
- **SUM(v.quantidade * p.preco_unitario)**: Calcula o valor total de vendas para cada produto.
- **GROUP BY**: Agrupa os resultados por produto.
- **ORDER BY**: Ordena os produtos com maior receita primeiro.

#### **Resultado**
| id_produto | nome_produto      | total_vendas |
|------------|-------------------|--------------|
| 3          | Mesa Compacta     | 2500.00      |
| 1          | Notebook Ultra    | 6000.00      |
| 2          | Smartphone Pro    | 2000.00      |

---

### **LEFT JOIN: Produtos Não Vendidos**

O **LEFT JOIN** retorna todos os registros da tabela da esquerda (base) e adiciona os dados correspondentes da tabela da direita. Se não houver correspondência, os valores da tabela direita são **NULL**.

#### **Caso de Negócio: Produtos Nunca Vendidos**

Queremos listar os produtos cadastrados que nunca geraram uma venda. Isso ajuda a identificar itens que precisam de atenção em estratégias de marketing.

#### **Query**
```sql
SELECT 
    p.id_produto, 
    p.nome_produto, 
    p.categoria, 
    p.preco_unitario
FROM produtos p
LEFT JOIN vendas v ON p.id_produto = v.id_produto
WHERE v.id_produto IS NULL;
```

#### **Explicação**
- **LEFT JOIN**: Inclui todos os produtos, mesmo aqueles sem correspondência na tabela `vendas`.
- **WHERE v.id_produto IS NULL**: Filtra os produtos que não possuem vendas (os valores NULL indicam ausência de correspondência).

#### **Resultado**
| id_produto | nome_produto        | categoria       | preco_unitario |
|------------|---------------------|-----------------|----------------|
| 4          | Cadeira Ergonômica | Móveis          | 600.00         |
| 5          | Monitor Full HD    | Eletrônicos     | 800.00         |

---

### **RIGHT JOIN: Vendas Sem Cadastro no Catálogo**

O **RIGHT JOIN** mantém todos os registros da tabela da direita e adiciona os valores da esquerda quando há correspondência. Usamos para identificar vendas de produtos que não estão cadastrados no catálogo.

#### **Caso de Negócio: Produtos Não Cadastrados**

Queremos identificar os produtos vendidos, mas que não constam no catálogo de produtos.

#### **Query**
```sql
SELECT 
    v.id_produto, 
    COUNT(v.id_venda) AS total_vendas, 
    SUM(v.quantidade) AS total_quantidade
FROM produtos p
RIGHT JOIN vendas v ON p.id_produto = v.id_produto
WHERE p.id_produto IS NULL
GROUP BY v.id_produto;
```

#### **Explicação**
- **RIGHT JOIN**: Inclui todas as vendas, mesmo que o produto não esteja na tabela `produtos`.
- **WHERE p.id_produto IS NULL**: Filtra os produtos que estão nas vendas, mas não no catálogo.
- **GROUP BY**: Agrupa os resultados por `id_produto`.

#### **Resultado**
| id_produto | total_vendas | total_quantidade |
|------------|--------------|------------------|
| 80         | 1            | 3                |
| 123        | 1            | 5                |
| 444        | 1            | 2                |

---

### **Comparação dos JOINs**

| Tipo de JOIN | Objetivo                                   | Resultado                                                |
|--------------|-------------------------------------------|---------------------------------------------------------|
| **INNER JOIN** | Mostrar apenas os registros com correspondência | Produtos que foram vendidos                             |
| **LEFT JOIN**  | Mostrar todos os registros da tabela base  | Produtos cadastrados, mesmo sem vendas                  |
| **RIGHT JOIN** | Mostrar todos os registros da tabela relacionada | Vendas de produtos não cadastrados                     |

---

### **Contexto de Negócio**

Esses exemplos ilustram situações práticas no gerenciamento de dados de vendas e produtos:
- **INNER JOIN**: Usado para relatórios de produtos mais vendidos ou receita total.
- **LEFT JOIN**: Identifica lacunas no desempenho de produtos cadastrados.
- **RIGHT JOIN**: Detecta erros operacionais, como vendas de produtos não cadastrados.

Esses JOINs ajudam a garantir a consistência e a completude dos dados, além de apoiar decisões baseadas em análises confiáveis e detalhadas. 🚀
---

## **12. SUBQUERY – Consultas Aninhadas**

### **O que é uma Subquery?**
Uma **Subquery** é uma consulta SQL dentro de outra consulta. O resultado da Subquery é usado como entrada para a consulta externa.

### **Por que usar Subquery?**
- **Reutilização de consultas menores:** Uma Subquery permite usar os resultados de uma consulta diretamente dentro de outra.
- **Simplificação de cálculos:** Reduz a necessidade de cálculos manuais.
- **Análises avançadas:** Ideal para comparar um conjunto de dados com métricas agregadas, como médias ou totais.

### **Exemplo 1: Produtos com preço acima da média**
Queremos encontrar todos os produtos cujo preço unitário esteja acima da média.

```sql
SELECT * 
FROM produtos
WHERE preco_unitario > (SELECT AVG(preco_unitario) FROM produtos);
```

**Explicação:**
1. A Subquery `(SELECT AVG(preco_unitario) FROM produtos)` calcula o preço médio de todos os produtos.
2. A consulta externa compara cada `preco_unitario` com a média calculada na Subquery.

#### **Resultado Esperado**
| id_produto | nome_produto    | categoria       | preco_unitario |
|------------|-----------------|-----------------|----------------|
| 1          | Notebook Ultra  | Eletrônicos     | 3000.00        |
| 2          | Smartphone Pro  | Eletrônicos     | 2000.00        |

---

### **Exemplo 2: Clientes com mais vendas do que a média**
Queremos identificar clientes que realizaram mais compras do que a média de vendas por cliente.

```sql
SELECT id_cliente, COUNT(*) AS total_vendas
FROM vendas
GROUP BY id_cliente
HAVING COUNT(*) > (
    SELECT AVG(total_vendas) 
    FROM (
        SELECT id_cliente, COUNT(*) AS total_vendas 
        FROM vendas 
        GROUP BY id_cliente
    ) AS subquery
);
```

**Explicação:**
1. A Subquery interna calcula o número de vendas para cada cliente.
2. A segunda Subquery calcula a média de vendas entre todos os clientes.
3. A consulta externa filtra apenas os clientes com vendas acima da média.

---

## **13. CTE – Common Table Expressions**

### **O que é uma CTE?**
Uma **Common Table Expression (CTE)** é um bloco nomeado que armazena o resultado de uma consulta temporariamente, tornando consultas complexas mais organizadas e legíveis.

### **Por que usar CTE?**
- **Legibilidade:** Torna consultas longas mais fáceis de entender.
- **Reutilização:** Permite usar o mesmo resultado em várias partes de uma consulta.
- **Modularidade:** Divide consultas complexas em partes menores.

---

### **Exemplo 1: Produtos com preço acima da média usando CTE**

```sql
WITH preco_medio AS (
    SELECT AVG(preco_unitario) AS media_precos
    FROM produtos
)
SELECT * 
FROM produtos
WHERE preco_unitario > (SELECT media_precos FROM preco_medio);
```

**Explicação:**
1. A CTE `preco_medio` calcula a média dos preços dos produtos.
2. A consulta principal utiliza o valor calculado para filtrar os produtos com preço acima da média.

---

### **Exemplo 2: Análise de vendas por cliente usando CTE**

```sql
WITH vendas_por_cliente AS (
    SELECT id_cliente, COUNT(*) AS total_vendas
    FROM vendas
    GROUP BY id_cliente
)
SELECT * 
FROM vendas_por_cliente
WHERE total_vendas > (
    SELECT AVG(total_vendas) 
    FROM vendas_por_cliente
);
```

**Explicação:**
1. A CTE `vendas_por_cliente` calcula o número de vendas para cada cliente.
2. A consulta principal filtra os clientes que realizaram mais vendas do que a média calculada.

---

### **Comparação: Subquery vs CTE**
| **Critério**             | **Subquery**                              | **CTE**                                   |
|--------------------------|-------------------------------------------|-------------------------------------------|
| **Legibilidade**         | Menos legível em consultas complexas.     | Mais organizado e fácil de entender.      |
| **Reutilização**         | Não reutilizável em várias partes.        | Pode ser reutilizada na consulta principal. |
| **Desempenho**           | Similar em desempenho.                   | Similar em desempenho.                    |
| **Uso Ideal**            | Consultas simples ou isoladas.           | Consultas complexas com múltiplas etapas. |

---

## **14. VIEW – Consultas Reutilizáveis**

### **O que é uma VIEW?**
Uma **VIEW** é uma tabela virtual baseada em uma consulta SQL. Ela não armazena dados, mas executa a consulta subjacente sempre que é usada.

### **Por que usar VIEW?**
- **Reutilização de lógica:** Permite salvar consultas frequentes.
- **Simplificação:** Reduz a complexidade para os usuários finais.
- **Segurança:** Restringe o acesso a dados sensíveis.

---

### **Exemplo 1: Criando uma VIEW de vendas por cliente**

```sql
CREATE VIEW vendas_por_cliente AS
SELECT id_cliente, COUNT(*) AS total_vendas, SUM(quantidade) AS total_quantidade
FROM vendas
GROUP BY id_cliente;
```

### **Consultando a VIEW**

```sql
SELECT * FROM vendas_por_cliente
WHERE total_vendas > 10;
```

---

### **15. Criação de Tabelas**

Além de consultas, você pode criar novas tabelas para armazenar resultados.

### **Exemplo 1: Criando uma tabela com vendas agregadas**

```sql
CREATE TABLE vendas_agregadas AS
SELECT id_cliente, COUNT(*) AS total_vendas, SUM(quantidade) AS total_quantidade
FROM vendas
GROUP BY id_cliente;
```

---

### **Quando usar Subqueries, CTEs, Views ou Tabelas?**
| **Ferramenta** | **Uso Ideal**                                                             |
|----------------|---------------------------------------------------------------------------|
| **Subquery**   | Para consultas isoladas e cálculos diretos.                               |
| **CTE**        | Para dividir e organizar consultas complexas.                            |
| **VIEW**       | Para reutilizar consultas frequentes em diferentes contextos.            |
| **Tabela**     | Para armazenar resultados permanentes ou intermediários para análises.   |

Essas ferramentas são cruciais para manipular e estruturar dados de forma eficiente, especialmente em análises complexas.

---

## **Desafios de Negócio**

### **Desafios de Negócio**

1. **Produtos Mais Vendidos:** Identificar os produtos mais vendidos em termos de quantidade.
2. **Clientes Mais Lucrativos:** Determinar os clientes que mais gastaram.

Cada desafio será detalhado com o código SQL, o raciocínio por trás da solução, e o contexto de aplicação no negócio.

---

## **1. Produtos Mais Vendidos**

### **Objetivo de Negócio**
Queremos identificar os produtos mais vendidos para entender quais itens têm maior saída e, possivelmente, quais devem receber mais foco em estoque ou marketing.

### **Query**
```sql
SELECT 
    p.id_produto, 
    p.nome_produto, 
    SUM(v.quantidade) AS total_quantidade
FROM vendas v
INNER JOIN produtos p ON v.id_produto = p.id_produto
GROUP BY p.id_produto, p.nome_produto
ORDER BY total_quantidade DESC
LIMIT 10;
```

### **Explicação do Código**
1. **`INNER JOIN produtos p ON v.id_produto = p.id_produto`**: Relaciona as tabelas `vendas` e `produtos` para trazer os nomes dos produtos vendidos.
2. **`SUM(v.quantidade)`**: Calcula a quantidade total vendida para cada produto.
3. **`GROUP BY p.id_produto, p.nome_produto`**: Agrupa os resultados por produto para calcular os totais de cada item.
4. **`ORDER BY total_quantidade DESC`**: Ordena os produtos mais vendidos no topo.
5. **`LIMIT 10`**: Retorna apenas os 10 produtos mais vendidos.

---

### **Exemplo de Resultado**
| id_produto | nome_produto       | total_quantidade |
|------------|--------------------|------------------|
| 5          | Smartphone Pro     | 500              |
| 12         | Notebook Ultra     | 450              |
| 8          | Cadeira Ergonômica | 350              |

---

### **Contexto de Aplicação**
- **Marketing:** Priorizar produtos mais vendidos em campanhas promocionais.
- **Estoque:** Garantir que esses produtos estejam disponíveis para evitar rupturas.
- **Vendas:** Identificar tendências e ajustar o mix de produtos.

---

## **2. Clientes Mais Lucrativos**

### **Objetivo de Negócio**
Queremos descobrir quais clientes geraram mais receita para a empresa, permitindo que ações personalizadas sejam criadas para fidelizar ou recompensar esses clientes.

### **Query**
```sql
SELECT 
    v.id_cliente, 
    c.primeiro_nome, 
    c.ultimo_nome, 
    SUM(v.quantidade * p.preco_unitario) AS total_gasto
FROM vendas v
INNER JOIN produtos p ON v.id_produto = p.id_produto
INNER JOIN clientes c ON v.id_cliente = c.id_cliente
GROUP BY v.id_cliente, c.primeiro_nome, c.ultimo_nome
ORDER BY total_gasto DESC
LIMIT 10;
```

---

### **Explicação do Código**
1. **`INNER JOIN produtos p ON v.id_produto = p.id_produto`**: Relaciona as tabelas `vendas` e `produtos` para calcular o valor de cada venda.
2. **`INNER JOIN clientes c ON v.id_cliente = c.id_cliente`**: Adiciona informações dos clientes às vendas.
3. **`SUM(v.quantidade * p.preco_unitario)`**: Calcula o total gasto por cada cliente.
4. **`GROUP BY v.id_cliente, c.primeiro_nome, c.ultimo_nome`**: Agrupa os resultados por cliente para calcular os totais de cada um.
5. **`ORDER BY total_gasto DESC`**: Ordena os clientes mais lucrativos no topo.
6. **`LIMIT 10`**: Retorna apenas os 10 clientes mais lucrativos.

---

### **Exemplo de Resultado**
| id_cliente | primeiro_nome | ultimo_nome | total_gasto |
|------------|---------------|-------------|-------------|
| 101        | Ana           | Souza       | 15,000.00   |
| 202        | João          | Silva       | 12,500.00   |
| 303        | Maria         | Oliveira    | 10,000.00   |

---

### **Contexto de Aplicação**
- **Fidelização:** Criar programas de benefícios exclusivos para clientes mais lucrativos.
- **Segmentação:** Identificar padrões de consumo e criar campanhas direcionadas.
- **Insights de Negócio:** Entender o comportamento de compra dos principais clientes.

---

Esses dois desafios cobrem aspectos cruciais do negócio: identificar os produtos que movimentam o estoque e os clientes que mais contribuem para a receita. Eles ajudam a embasar estratégias em dados concretos, promovendo ações mais eficazes e direcionadas.
