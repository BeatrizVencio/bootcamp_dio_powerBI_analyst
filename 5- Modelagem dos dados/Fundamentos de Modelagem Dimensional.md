# Fundamentos de Modelagem Dimensional

### Aula 1 - Desmistificando a Modelagem Dimensional

A modelagem dimensional é uma técnica utilizada para organizar dados de forma a facilitar a análise e a tomada de decisões. É muito utilizada em sistemas de Business Intelligence (BI) e Data Warehousing. Apesar do nome "dimensional", ela não tem relação com matemática ou física!

**Por que utilizar modelagem dimensional?**

- **Performance:** Essa técnica é otimizada para consultas rápidas e eficientes, permitindo que você obtenha resultados em segundos, mesmo com grandes volumes de dados.
- **Escalabilidade:** A modelagem dimensional permite que você adicione novos dados facilmente, sem comprometer a performance.
- **Disponibilidade:** Se um servidor cair, você pode acessar os dados através de uma réplica, garantindo que as informações estejam sempre disponíveis para análise.

**Modelos de dados: OLTP e OLAP**

Existem dois modelos de dados principais: OLTP (On-Line Transaction Processing) e OLAP (On-Line Analytical Processing).

- **OLTP:** Esse modelo é focado em transações de alta velocidade, como vendas, cadastros e pagamentos.
    - *Características:* Fim específico, cenários otimizados para transações e suporte à operação.
    - *Exemplo:* Bancos de dados relacionais (SGBDs), como MySQL, PostgreSQL e Oracle.
- **OLAP:** Esse modelo é focado em análises complexas, respondendo perguntas sobre o negócio a partir de grandes volumes de dados.
    - *Características:* Permite redundâncias, esquema flexível, foco em análises e modelo em cubo.
    - *Exemplo:* Modelagem Dimensional.

**A modelagem dimensional é ideal para OLAP porque:**

- Permite consultas complexas de forma rápida e eficiente, com foco na análise e insights.
- É fácil de entender e trabalhar, mesmo para pessoas que não são especialistas em bancos de dados.
- Permite que você utilize diferentes dimensões para analisar os dados, criando uma visão completa do negócio.

### Aula 2 - O que significa Modelagem em Cubo?

**O que é o modelo em cubo?**

Imagine um cubo com três dimensões:

- **Eixo X:** Representa uma dimensão, como "produto".
- **Eixo Y:** Representa outra dimensão, como "país".
- **Eixo Z:** Representa uma terceira dimensão, como "data".

Cada face desse cubo representa uma "visão" diferente dos dados. Por exemplo, a face do "produto" e "país" mostraria a performance de vendas de cada produto em cada país.

**Formalizando o cubo**

Em termos mais técnicos, o modelo em cubo se caracteriza por:

- **Eixos:** Representam os componentes do esquema, como "produto", "data", "país" em nosso exemplo.
- **Interseção:** Representam as medidas e dados do contexto, como o valor da venda de um determinado produto em um país específico em uma data específica.
- **Visão consolidada:** Um cubo fornece uma visão consolidada do contexto, permitindo analisar os dados de diferentes ângulos, em comparação a uma tabela que fornece uma visão limitada.
- **Análises de perspectivas distintas:** O cubo permite analisar dados de diferentes perspectivas, combinando os eixos e seus valores.

**Tabular vs. Dimensional**

Vamos comparar o modelo tabular tradicional com o dimensional em cubo:

- **Tabular:** Uma tabela funciona como um plano bidimensional (linhas e colunas), restringindo as combinações e análises a duas dimensões.
- **Dimensional:** O cubo, com suas três dimensões, permite uma flexibilidade maior na análise de dados, combinando diferentes aspectos e extraindo insights mais profundos.

**Por que é útil?**

O modelo em cubo é útil para:

- **Analises multidimensionais:** Permite combinar múltiplas dimensões para responder perguntas complexas.
- **Insights profundos:** Permite extrair insights e padrões ocultos nos dados, que seriam difíceis de encontrar em uma tabela.
- **Agilidade e velocidade:** O modelo em cubo é otimizado para consultas rápidas, permitindo que você obtenha resultados em segundos.

### Aula 3 - Entendendo Modelagem com Start Schema

Agora, vamos conhecer o **Star Schema**, um dos esquemas mais populares para implementar a modelagem dimensional em cubos.

**O que é o Star Schema?**

O Star Schema, ou Esquema em Estrela, é um esquema de banco de dados que se assemelha a uma estrela, com uma **tabela Fact (Fatos)** no centro e várias **tabelas Dimension (Dimensões)** ao redor, como raios.

- **Tabela Fact:** Concentra as principais medidas do negócio, como valores de vendas, quantidades, custos, etc. É como o "núcleo" do cubo, contendo as informações quantitativas.
- **Tabelas Dimension:** Armazenam informações contextuais sobre os fatos, como detalhes de produtos, clientes, países, datas, etc. São como os "eixos" do cubo, fornecendo o contexto para análise.

**Vantagens do Star Schema:**

- **Facilidade de entendimento:** O esquema é simples e intuitivo, tornando a análise de dados mais acessível.
- **Consultas rápidas:** A estrutura otimizada facilita consultas complexas e permite que você obtenha resultados rapidamente.
- **Escalabilidade:** Adicionar novas dimensões é relativamente fácil, expandindo a capacidade de análise sem comprometer a performance.

**Exemplo de Star Schema:**

Imagine uma empresa que vende produtos online. Um Star Schema para essa empresa poderia ter:

- **Tabela Fact (Sales):** Contém as informações sobre as vendas, como data, produto, cliente, quantidade vendida, valor total.
- **Tabela Dimension (Customer):** Detalha informações sobre os clientes, como nome, endereço, cidade, país.
- **Tabela Dimension (Product):** Contém detalhes sobre os produtos, como nome, descrição, categoria.
- **Tabela Dimension (Time):** Armazena informações sobre o tempo, como ano, mês, dia da semana, etc.

**Relações no Star Schema:**

As tabelas Dimension se relacionam com a tabela Fact através de chaves estrangeiras (FKs). Essas FKs representam o "contexto" da medida da tabela Fact.

### Aula 4 - Tipos de modelos dimensionais: Start Schema, Snowflake e Constellation

Agora, vamos explorar outros tipos de modelos dimensionais, cada um com suas particularidades.

**1. Snowflake Schema (Esquema de Floco de Neve):**

- O Snowflake Schema é uma variação do Star Schema, com um nível de normalização maior, ou seja, há mais tabelas dimensionais.
- As tabelas dimensionais, além de se conectarem diretamente à Fact Table, também se relacionam entre si, formando uma estrutura hierárquica que lembra um floco de neve.
- Isso pode melhorar a organização e a consistência dos dados, mas pode complicar um pouco as consultas e aumentar o tempo de processamento.

**Exemplo:**

Em um Snowflake Schema, a tabela "Dealer" pode ter uma relação com a tabela "Location" (Localização) e a tabela "Location" pode ter uma relação com a tabela "Region" (Região).

**2. Constellation Schema (Esquema de Constelação):**

- O Constellation Schema é um esquema mais flexível que permite diferentes tabelas Fact conectadas às mesmas tabelas Dimension.
- Essa estrutura é ideal para cenários onde há necessidade de analisar diferentes aspectos do negócio em um único data warehouse.
- Por exemplo, a tabela Fact "Sales" (Vendas) pode estar conectada à mesma tabela Dimension "Product" (Produto) que a tabela Fact "Inventory" (Estoque).

**Comparando os Esquemas:**

- **Star Schema:** Ideal para consultas rápidas e simples, com menor complexidade na estrutura.
- **Snowflake Schema:** Oferece maior normalização e organização, mas pode impactar o tempo de consulta.
- **Constellation Schema:** Oferece flexibilidade para analisar diferentes aspectos do negócio em um único data warehouse.

**Escolha do modelo:**

A escolha do modelo ideal depende da complexidade do seu negócio e dos requisitos de análise.

- **Star Schema:** Ideal para empresas com um volume menor de dados e consultas simples.
- **Snowflake Schema:** Indicado para empresas com um volume maior de dados e que precisam de maior organização e normalização.
- **Constellation Schema:** Ideal para empresas com cenários mais complexos que exigem a análise de diferentes aspectos do negócio em um único data warehouse.

### Aula 5 - Explorando Brevemente os Modelos Dimensionais

Agora, vamos aprofundar o conhecimento sobre o **Star Schema**, o modelo mais popular e que serve como base para outros esquemas.

**Modelo Estrela:**

- **Conexão das tabelas em forma de estrela:** Esse esquema se destaca pela sua estrutura simples e intuitiva, que facilita o entendimento e as consultas.
- **Dois tipos de tabelas:**
    - **Tabela Fact (Fatos):** Concentra as principais medidas do negócio, como valores de vendas, quantidades, custos, etc.
    - **Tabela Dimension (Dimensões):** Armazenam informações contextuais sobre os fatos, como detalhes de produtos, clientes, países, datas, etc.

**Características:**

- **Chave Artificial:** O Star Schema utiliza chaves artificiais (IDs) para relacionar as tabelas Dimension à tabela Fact, garantindo que as informações estejam organizadas de forma consistente.
- **Mapeamento com desnormalização:** A desnormalização, ou seja, a repetição de dados, é permitida para otimizar a performance das consultas, sem prejudicar a integridade.
- **PKs (Primary Keys) simples e dados exclusivos:** Cada tabela Dimension possui uma PK simples e única, o que facilita a identificação e a relação entre os dados.

**Vantagens do Modelo Estrela:**

- **Performance:** A estrutura simplificada e desnormalizada otimiza as consultas e permite que você obtenha resultados em segundos.
- **Escalabilidade:** É fácil adicionar novas tabelas Dimension, expandindo a capacidade de análise sem comprometer a performance.
- **Facilidade de implementação:** O Star Schema é fácil de entender e implementar, tornando-o uma escolha popular para empresas que desejam construir um data warehouse eficiente.

### Aula 6 - O que é Granularidade de dados?

Agora, vamos entender um conceito fundamental para a modelagem dimensional: a **granularidade dos dados**.

**O que é Granularidade?**

Granularidade se refere ao **nível de detalhamento dos dados** em uma tabela Fact. Pense como se você estivesse "zoomando" para dentro dos dados:

- **Grão Grosso (Menos Detalhe):** Você tem uma visão geral, com poucos detalhes e dados agregados. Imagine um mapa do mundo.
- **Grão Fino (Mais Detalhe):** Você tem uma visão mais específica, com muitos detalhes e informações individuais. Imagine um mapa de rua.

**Como definir a granularidade?**

Definir a granularidade ideal é crucial para a modelagem dimensional, pois impacta:

- **Performance:** Uma granularidade muito fina pode sobrecarregar o sistema, tornando as consultas lentas e ineficientes.
- **Armazenamento:** Uma granularidade muito fina exige mais espaço de armazenamento.

**Trade-off na definição:**

É importante encontrar um equilíbrio entre a granularidade e o desempenho do sistema.

**Exemplo:**

Imagine que você está analisando vendas de produtos online.

- **Granularidade por mês:** Você terá uma visão geral das vendas ao longo do tempo.
- **Granularidade por dia:** Você terá uma visão mais detalhada, mostrando as vendas em cada dia do mês.
- **Granularidade por hora:** Você terá uma visão ainda mais detalhada, mostrando as vendas em cada hora do dia.

A escolha da granularidade depende do **objetivo da análise**. Se você precisa de uma visão geral das vendas, uma granularidade por mês pode ser suficiente. Mas se você precisa de uma visão mais detalhada, pode ser necessário usar uma granularidade por dia ou até mesmo por hora.

### Aula 7 - Chave Artificial com Start Schema

Agora, vamos discutir a **chave artificial (Surrogate Key)**, um componente importante do Star Schema.

**O que é a chave artificial?**

A chave artificial é um **identificador numérico único**, gerado pelo sistema, para cada registro na tabela Fact e nas tabelas Dimension.  Ela serve como um substituto para a chave natural (que pode ser um código, um nome, um número de série, etc.), que vem do sistema original de dados.

**Por que usar a chave artificial?**

- **Identificação sem sobreposição:** A chave artificial garante que cada registro tenha um identificador único, mesmo que a chave natural seja repetida em diferentes sistemas.
- **Facilita a identificação:** As chaves artificiais são geralmente numéricos, tornando a identificação e a busca por registros mais rápidas e eficientes, especialmente em grandes conjuntos de dados.

**Exemplo:**

Imagine que você está importando dados de vendas de um sistema antigo para um data warehouse.  No sistema antigo, a chave para identificar o cliente pode ser o nome completo.

No Star Schema, você pode criar uma chave artificial chamada "Customer_ID" (ID do Cliente) que atribui um número único a cada cliente,  mesmo que alguns clientes tenham o mesmo nome.

### Aula 8 - Rastreando Modificações no Modelo - Slowly Changing Dimensions

Na aula anterior, desvendamos a chave artificial e sua importância no Star Schema.

Agora, vamos explorar um conceito essencial para lidar com as mudanças temporais nos dados: **Slowly Changing Dimensions (SCDs)**.

**O que são SCDs?**

SCDs são métodos para **registrar as modificações** que acontecem em tabelas Dimension ao longo do tempo. Imagine um cenário onde você precisa rastrear a mudança de cargo de um funcionário ou a alteração no preço de um produto.

**Tipos de SCDs:**

Existem diferentes tipos de SCDs, cada um com uma abordagem específica para registrar as mudanças:

- **SCD-0 (Tipo 0):** O mais simples e passivo. Não há registro histórico das mudanças. Quando um atributo é alterado, a informação antiga é simplesmente sobrescrita pela nova.
    - *Exemplo:* Se o funcionário "João" troca de cargo de "Analista" para "Gerente", o registro é atualizado na tabela Dimension.
- **SCD-1 (Tipo 1):** A informação antiga é sobrescrita pela nova, mas o histórico não é mantido. Ideal para atributos que mudam raramente.
    - *Exemplo:* Se o preço de um produto muda, o novo preço é gravado na tabela Dimension, mas a informação sobre o preço anterior é perdida.
- **SCD-2 (Tipo 2):** A informação antiga é mantida em um novo registro, com datas de início e fim, criando um histórico das mudanças.
    - *Exemplo:* Se o funcionário "João" muda de cargo, a tabela Dimension terá dois registros: um com a informação antiga (Cargo: "Analista", Data de início: "2021-01-01", Data de fim: "2022-12-31") e outro com a informação nova (Cargo: "Gerente", Data de início: "2023-01-01", Data de fim: "NULL").
- **SCD-3 (Tipo 3):** Cria uma nova coluna para armazenar a informação antiga, mantendo o histórico das mudanças.
    - *Exemplo:* Se o funcionário "João" muda de cargo, a tabela Dimension terá uma nova coluna chamada "PreviousDesignation" (Cargo Anterior).
- **SCD-4 (Tipo 4):** A informação antiga é armazenada em uma nova tabela, mantendo o histórico completo das mudanças.
    - *Exemplo:* Quando o funcionário "João" muda de cargo, o registro antigo é copiado para uma nova tabela.
- **SCD-6 (Tipo 6):** Combina os tipos SCD-1, SCD-2 e SCD-3. É um tipo mais complexo, mas oferece uma flexibilidade maior.

### Materiais Complementares

[Introdução a Modelagem Dimensional.pptx](https://github.com/BeatrizVencio/bootcamp_dio_powerBI_analyst/blob/main/5-%20Modelagem%20dos%20dados/materiais%20complementares/Introdução%20a%20Modelagem%20Dimensional.pptx)
