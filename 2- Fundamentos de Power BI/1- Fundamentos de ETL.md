# Fundamentos de ETL

### Aula 1 - O que é ETL (Extract, Transform and Load)

**Breve descrição do contexto**

- Imagine um cenário em que você precisa juntar dados de diferentes fontes para analisá-los e tomar decisões mais assertivas. Essa é a realidade da maioria das empresas que trabalham com BI (Business Intelligence) e que precisam de um processo eficiente para tratar e organizar seus dados.

**ETL - Extract, Transform and Load?**

- ETL é uma sigla em inglês que significa "Extrair, Transformar e Carregar". Esse processo é fundamental para o tratamento e organização de dados em BI. Ele envolve três etapas principais:
    1. **Extração (Extract):** Extrair dados de diferentes fontes, como bancos de dados, arquivos, sistemas legados, clouds, etc.
    2. **Transformação (Transform):** Tratar os dados extraídos, limpando-os, padronizando-os e organizando-os em um formato único.
    3. **Carregamento (Load):** Carregar os dados transformados para um repositório final, como um data warehouse, data lake ou um banco de dados.

**ELT - Extract, Load and Transform?**

- ELT é uma variação do processo ETL em que a etapa de transformação acontece após o carregamento dos dados. Isso significa que os dados são extraídos e carregados para um repositório final sem tratamento prévio. A transformação é feita no repositório final,  o que pode ser mais vantajoso para grandes volumes de dados e para cenários em que a análise é mais complexa.

**Diferenças entre ETL e ELT:**

| Característica | ETL | ELT |
| --- | --- | --- |
| Ordem das etapas | Extract > Transform > Load | Extract > Load > Transform |
| Transformação | Realizada antes do carregamento | Realizada após o carregamento |
| Volumes de dados | Ideal para volumes menores | Ideal para volumes maiores |
| Complexidade da análise | Análise mais simples | Análise mais complexa |

**Vantagens do ETL:**

- **Qualidade dos dados:** O ETL garante a qualidade dos dados ao limpá-los e padronizá-los antes de serem armazenados.
- **Organização:** Os dados são organizados em um formato único, facilitando a análise e a extração de insights.
- **Eficiência:** A transformação prévia reduz o tempo e o esforço necessário para analisar os dados.

**Vantagens do ELT:**

- **Escalabilidade:** O ELT é mais escalável para lidar com grandes volumes de dados.
- **Flexibilidade:** Permite que os dados sejam transformados de acordo com as necessidades da análise, sem a necessidade de reprocessar todo o conjunto de dados.
- **Tempo de resposta:** O ELT oferece um tempo de resposta mais rápido para consultas, pois os dados são carregados diretamente para o repositório final.

**Quando usar ETL ou ELT?**

- A escolha entre ETL e ELT depende das necessidades específicas do projeto.  Se você precisar de dados de alta qualidade e  análise rápida,  o ETL é a melhor opção.  Se você precisar de mais flexibilidade e  escalabilidade para grandes volumes de dados,  o ELT pode ser mais adequado.

### Aula 2 - O que é ELT (Extract, Load and Transform)

**ELT - Extract, Load and Transform**

- O ELT, como já vimos, é uma variação do processo ETL, que inverte a ordem das etapas de transformação e carregamento.  Em vez de transformar os dados antes de carregá-los, o ELT faz o carregamento direto para um repositório final, geralmente um data lake, e a transformação é realizada posteriormente nesse repositório.

**Processos de ETL vs. ELT:**

| Processo | Descrição |
| --- | --- |
| ETL | Extrai, Transforma e Carrega. A transformação acontece antes do carregamento. |
| ELT | Extrai, Carrega e Transforma. A transformação acontece após o carregamento. |

**Load, Transform e Vantagens do ELT:**

- **Load:** O carregamento dos dados no ELT é um processo relativamente simples, pois os dados são carregados sem tratamento prévio.
- **Transform:** A transformação é realizada no repositório final, geralmente utilizando ferramentas de big data, como o Hadoop ou Spark.
- **Vantagens:** O ELT oferece diversas vantagens em relação ao ETL, especialmente para lidar com grandes volumes de dados.
    - **Escalabilidade:** O ELT é mais escalável, pois a transformação é feita no repositório final, que é projetado para lidar com grandes volumes de dados.
    - **Flexibilidade:** A transformação é feita após o carregamento, o que permite uma maior flexibilidade para definir as transformações de acordo com as necessidades da análise.
    - **Agilidade:** O ELT pode ser mais ágil em termos de tempo de resposta para consultas, pois os dados são carregados diretamente para o repositório final, sem a necessidade de etapas de transformação prévias.

**Entendendo as Diferenças entre ETL e ELT:**

- **Abordagem de transformação:** O ETL transforma os dados antes de carregá-los, enquanto o ELT transforma os dados após o carregamento.
- **Perspectiva sobre os dados:** O ETL foca na qualidade dos dados antes do carregamento, enquanto o ELT permite que os dados sejam transformados de acordo com a análise.
- **Estrutura influencia na análise:** A estrutura dos dados no ELT pode influenciar na forma como a análise é realizada.

**Quando usar ELT?**

O ELT é ideal para cenários com:

- **Grandes volumes de dados:** O ELT é mais eficiente para lidar com grandes volumes de dados, pois a transformação é realizada no repositório final.
- **Análise complexa:** O ELT permite que os dados sejam transformados de acordo com as necessidades da análise, o que é ideal para análises mais complexas.
- **Tempo de resposta:** O ELT oferece um tempo de resposta mais rápido para consultas, pois os dados são carregados diretamente para o repositório final, sem a necessidade de etapas de transformação prévias.

### Aula 3 - Processo de Extração de Dados (ELT)

**Processo de Extração de Dados - ELT**

**Extração:**

Nessa etapa, os dados brutos, ainda sem estrutura definida, são coletados de diversas fontes heterogêneas.  Exemplos de fontes:

- **Bancos de dados relacionais (RDBMS):** Sistemas de gerenciamento de bancos de dados relacionais, como SQL Server, Oracle, MySQL.
- **Clouds:** Serviços de computação em nuvem, como AWS, Azure, Google Cloud.
- **Files:** Arquivos de diversos formatos (CSV, XML, JSON).
- **APIs:** Interfaces de programação de aplicações.
- **Sistemas legados:** Sistemas mais antigos, que podem ser difíceis de integrar com os sistemas modernos.
- **CRMs:** Softwares de gerenciamento de relacionamento com o cliente.
- **Filas:** Sistemas de mensagens e eventos.

O objetivo principal da extração no ELT é a integração posterior dos dados,  unindo informações de diversas fontes em um repositório centralizado.

**Dados Estruturados x Dados Não Estruturados:**

- **Dados Estruturados:** Possuem uma organização definida, com um formato pré-determinado. Ex: Dados em tabelas com colunas e linhas.
- **Dados Não Estruturados:** Não possuem uma estrutura definida, podendo ter formatos variados. Ex: Textos, imagens, vídeos, áudios.

**Processo de Extração em Bancos de Dados Relacionais:**

Em bancos de dados relacionais,  o processo de extração envolve:

- **Definição do esquema:** Definir a estrutura da tabela, especificando as colunas, tipos de dados e constraints.
- **Coleta de informações:** Extrair os dados brutos do banco de dados, obedecendo às definições do esquema.

**Importância da Integração:**

A integração dos dados extraídos é fundamental para o sucesso do ELT.  Ela permite que informações de diversas fontes sejam combinadas,  formando um conjunto de dados completo e útil para a análise.

### Aula 4 - Load, Transform e Vantagens do ELT

**Load, Transform e Vantagens do ELT**

Nesta aula, vamos aprofundar a compreensão do ELT,  abordando as etapas de carregamento (Load) e transformação (Transform),  e  destacando as principais vantagens do processo.

**Load - Transferência/Carregamento dos Dados Brutos**

- **O Load:** É a etapa em que os dados brutos, coletados na etapa de extração, são transferidos para o repositório centralizado, geralmente um data warehouse ou um data lake.
- **Dados Brutos:** Os dados carregados no ELT ainda não foram tratados ou transformados.
- **Data Warehouse:** Um repositório centralizado de dados estruturados, projetado para análise e relatórios.
- **Data Lake:** Um repositório centralizado de dados não estruturados, armazenados em formato bruto para análise posterior.

**Transform - Transformação dos Dados dentro do Repositório**

- **Transform:** A transformação dos dados acontece **após** o carregamento no repositório centralizado. Utilizando ferramentas e técnicas de big data, como o Hadoop e Spark, os dados brutos são limpos, padronizados, transformados e agrupados em formatos adequados para a análise.
- **Ferramentas de Big Data:** Ferramentas especializadas no tratamento e análise de grandes volumes de dados.
    - **Hadoop:** Um framework de software de código aberto para processamento distribuído.
    - **Spark:** Um framework de computação distribuída de código aberto para processamento de dados em tempo real e em lote.
- **Análise de Dados:** Os dados transformados estão prontos para análise por profissionais de BI, analistas de dados e cientistas de dados.

**Vantagens do ELT:**

O ELT  oferece diversas vantagens em relação ao ETL,  especialmente em cenários com grandes volumes de dados e  análises complexas:

- **Otimização de tempo:** O ELT é mais eficiente em termos de tempo, pois a transformação é realizada no repositório final, o que permite que os dados sejam carregados rapidamente.
- **Eficiência na implementação de projetos:** O ELT reduz a complexidade da implementação de projetos, pois a transformação é feita em uma etapa posterior.
- **Menor dependência de TI:** A transformação é feita pelos analistas de dados, o que reduz a dependência da equipe de TI.
- **Papel principal dos analistas:** Os analistas de dados desempenham um papel fundamental no ELT, realizando a transformação dos dados para análise.
- **Contato direto com regras de negócios:** Os analistas de dados têm contato direto com as regras de negócios, o que permite que a transformação dos dados seja mais precisa e adequada às necessidades da empresa.

### Aula 5 - Diferenças entre ETL e ELT

**Eficiência e Escolha do Processo:**

Tanto o ETL quanto o ELT visam a mesma finalidade:  organizar e manipular dados para torná-los mais eficientes para análise e tomada de decisão. A diferença crucial está na ordem das etapas,  o que afeta a eficiência de cada processo em diferentes cenários.

**Vantagens do ELT:**

- **Tempo de carregamento:** O ELT é mais rápido no carregamento de dados, pois não precisa de transformação prévia.
- **Tempo de transformação:** A transformação é mais rápida no ELT, pois é feita em uma etapa posterior, utilizando ferramentas de big data.
- **Tempo de manutenção:** O ELT tem menor tempo de manutenção, pois a transformação não precisa ser refeita em cada atualização de dados.
- **Complexidade de implementação:** O ELT pode ser mais simples de implementar, pois a transformação é feita em uma etapa posterior.

**Limitações do ELT:**

- **Limitação de dados:** O ELT pode ter limitações no tratamento de dados que exigem transformação prévia, como limpeza de dados inválidos.
- **Suporte a Data Warehouses:** O ELT pode ter menos suporte a Data Warehouses, dependendo da ferramenta utilizada.
- **Usabilidade:** A usabilidade do ELT pode ser mais complexa para profissionais que não têm familiaridade com ferramentas de big data.

**Quando usar ETL ou ELT?**

A escolha entre ETL e ELT  depende das necessidades específicas da empresa,  levando em consideração:

- **Volume de dados:** Para grandes volumes de dados, o ELT é mais eficiente.
- **Complexidade da análise:** Para análises complexas que exigem flexibilidade, o ELT é uma boa opção.
- **Recursos da empresa:** O ETL pode ser mais caro, enquanto o ELT pode ser mais barato, dependendo da ferramenta utilizada.

### Aula 6 - Quando usar ETL ou ELT?

**Qual escolher? ETL ou ELT?**

A pergunta de um milhão de reais!  Após entendermos os conceitos básicos de ETL e ELT,  é hora de decidir qual abordagem se encaixa melhor nas necessidades do seu projeto de BI.

**Foco do ETL:**

O ETL  foi criado com foco na transformação dos dados.  Ele é mais indicado quando:

- **Armazenamento de dados é um desafio:** O ETL prioriza a qualidade dos dados antes do armazenamento, o que é crucial quando o armazenamento é caro ou complexo.
- **Tempo de resposta rápido:** O ETL é ideal quando você precisa de dados de alta qualidade e tempo de resposta rápido para consultas, o que pode ser importante para relatórios e análises em tempo real.
- **Escassez de recursos:** O ETL pode ser mais adequado para empresas com recursos limitados, pois a transformação é feita antes do carregamento, o que exige menos conhecimento de ferramentas de big data.

**Foco do ELT:**

O ELT  foi desenvolvido para lidar com grandes volumes de dados e  análises complexas,  com foco na flexibilidade:

- **Grandes volumes de dados:** O ELT é ideal para lidar com grandes volumes de dados, pois a transformação é feita após o carregamento.
- **Análise complexa:** O ELT permite que os dados sejam transformados de acordo com as necessidades da análise.
- **Agilidade em operações:** O ELT é mais ágil, pois o carregamento é feito rapidamente, e a transformação é feita posteriormente.
- **Baixo custo de armazenamento:** O ELT é mais econômico para empresas com baixos custos de armazenamento, pois os dados são carregados sem tratamento prévio.

**Decisão - ETL ou ELT?**

Em última análise, a escolha entre ETL e ELT  depende dos seguintes fatores:

- **Volume de dados:** Quanto maior o volume de dados, maior a probabilidade de o ELT ser mais eficiente.
- **Complexidade da análise:** Se a análise for complexa e exigir flexibilidade, o ELT é uma boa opção.
- **Recursos da empresa:** Se a empresa tiver recursos limitados para investir em ferramentas de big data, o ETL pode ser mais adequado.

### Materiais Complementares

[Curso 3 - Fundamentos de Processamento em Dados.pdf](https://github.com/BeatrizVencio/bootcamp_dio_powerBI_analyst/blob/main/2-%20Fundamentos%20de%20Power%20BI/Materiais%20Complementares/Curso%203%20-%20Fundamentos%20de%20Processamento%20em%20Dados.pdf)
