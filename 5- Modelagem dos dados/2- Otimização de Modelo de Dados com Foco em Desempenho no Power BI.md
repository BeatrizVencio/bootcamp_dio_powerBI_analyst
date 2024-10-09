# Otimização de Modelo de Dados com Foco em Desempenho no Power BI

### Aula 1 - O que é otimização no Power BI?

Otimização no Power BI é o processo de **realizar modificações no estado atual do modelo de dados para que suas operações sejam executadas com maior eficiência.** Dessa forma, **aumenta-se o desempenho** do modelo de dados, do relatório e do aplicativo, garantindo uma **melhor experiência do usuário**, **resultados mais rápidos** e **um cliente satisfeito.**

**Por que a otimização é importante?**

- Um relatório, por exemplo, pode ser bem feito, intuitivo e com bons resultados, mas ter baixa performance.
- Na fase de testes, o relatório pode funcionar bem, mas quando implementado, pode apresentar problemas de desempenho.
- Um relatório pode ser bem executado em um ambiente de testes, mas quando implantado em produção, pode ter problemas de desempenho.

**O que impacta na visão do usuário?**

O desempenho do relatório impacta na **experiência do usuário** e o usuário pode ter uma **experiência negativa**. O usuário pode sentir:

- **Lentidão no carregamento**
- **Demora na atualização dos visuais**

**O que causa a baixa performance?**

- **Modelagem inadequada**
- **Mau uso da linguagem DAX**
- **Combinação de ambos**

**Quais as vantagens da otimização?**

- **Melhor experiência do usuário**
- **Desempenho e bons resultados**
- **Cliente satisfeito**

**O processo de otimização no Power BI**

O processo de otimização é **essencial para um bom desempenho do relatório** e inclui:

- **Garantir que os tipos de dados corretos sejam usados:** é preciso garantir que os tipos de dados que estão sendo usados são os corretos para as operações que você está realizando. Por exemplo, se você está usando um tipo de dado inteiro para armazenar um valor decimal, você pode ter problemas de arredondamento ou perda de precisão.
- **Excluir colunas e linhas desnecessárias:** Isso ajuda a reduzir o tamanho do modelo de dados e a melhorar a velocidade de consulta.
- **Evitar valores repetidos:** Valores repetidos podem aumentar o tamanho do modelo de dados e prejudicar a velocidade de consulta.
- **Substituir colunas numéricas por medidas:** Medidas são mais eficientes para cálculos complexos do que colunas numéricas.
- **Reduzir cardinalidades:** Cardinalidade refere-se ao número de valores distintos em uma coluna. Uma baixa cardinalidade significa que a coluna tem menos valores distintos, o que pode melhorar a velocidade de consulta.
- **Analisar metadados do modelo:** Isso ajuda a entender como os dados são armazenados e como o modelo de dados está sendo usado.
- **Resumir dados sempre que possível:** Resumir os dados reduz o tamanho do modelo de dados e aumenta a velocidade de consulta.

**Armazenamento de Dados**

- **Importar:** Importar os dados para o Power BI e armazená-los localmente, o que permite um acesso rápido e fácil.
- **DirectQuery:** Consultar diretamente a fonte de dados, o que pode ser útil para grandes volumes de dados.
- **Composto:** Combinar a importação e DirectQuery, o que permite ter o melhor dos dois mundos.

**Esses métodos oferecem diferentes vantagens em termos de:**

- **Facilidade de acesso:** Importar é a opção mais fácil.
- **Tempo de carregamento:** DirectQuery é mais rápido para consultas complexas.
- **Permissão de acesso:** Importar é mais seguro, pois os dados são armazenados localmente.

A otimização é um processo **contínuo e iterativo**. À medida que seus dados crescem e seus requisitos de negócios mudam, você precisa otimizar seu modelo de dados para garantir que ele continue a funcionar de forma eficiente.

### Aula 2 - Exemplificando um cenário com problemas e otimização

**Cenário Hipotético:**

- **Relatório Visual Atraente:** O relatório foi bem projetado com visualizações e insights relevantes.
- **Resultados Significativos:** O relatório apresenta resultados importantes para a análise.
- **Comentários Negativos:** Apesar dos aspectos positivos, o relatório recebe comentários negativos por conta do seu desempenho.
- **Problema:** O modelo de dados utilizado para o relatório é ineficiente, levando a um desempenho ruim, como carga lenta, atualizações lentas e uso excessivo de armazenamento.

**Quais os Problemas?**

- O carregamento das páginas é lento.
- As tabelas não são atualizadas com rapidez em seleções.
- O arquivo do relatório está muito grande (tamanho do arquivo .pbix).

**O que fazer para resolver?**

- **Examinar o Desempenho:** Analisar o desempenho de medidas, relações e visuais.
- **Variáveis:** Utilizar variáveis para aprimorar o desempenho e solucionar problemas.
- **Aprimorar o Desempenho:** Reduzir os níveis de cardinalidade (número de valores distintos) dentro das tabelas.
- **Otimizar o DirectQuery:** Usar o DirectQuery com armazenamento no nível da tabela para melhorar a performance de consulta.
- **Agregações:** Criar e gerenciar agregações (agrupamentos de dados) para reduzir o tempo de processamento.

**Como Resolver?**

- **Identificação de Gargalos:** Determinar os pontos que causam o baixo desempenho do relatório (por exemplo, tabelas grandes, visuais complexos).
- **Performance Analyzer:** Utilizar a ferramenta Performance Analyzer para analisar o desempenho do relatório e identificar os gargalos.
- **Examinar os Resultados:** Analisar se os resultados obtidos com as análises são realmente necessários para o relatório.

**Pontos Importantes:**

- **Experiência do Usuário:** A experiência ruim do usuário com um relatório pode levar a uma baixa taxa de utilização e perda de valor da BI.
- **Modelo de Dados:** A otimização do modelo de dados é fundamental para garantir o desempenho e a eficiência do relatório.
- **Ferramentas:** Ferramentas como o Performance Analyzer podem auxiliar na identificação e resolução de problemas de desempenho.

**Objetivo:**

- Demonstrar como identificar problemas de desempenho em um relatório de BI.
- Apresentar soluções para otimizar o modelo de dados e melhorar o desempenho do relatório.
- Enfatizar a importância da experiência do usuário e do desempenho do relatório para o sucesso da BI.

**Conclusão:**

A otimização do modelo de dados é crucial para a construção de relatórios de BI eficientes e que proporcionam uma experiência positiva para o usuário. As técnicas de otimização apresentadas nesta aula podem ajudar a solucionar problemas de desempenho e maximizar o valor da BI dentro de uma organização.

### Aula 3 - Quando ocorrem os problemas de otimização?

**Visuais:**

- **Otimização:** Identificar gargalos de desempenho e otimizar os visuais para reduzir o impacto na experiência do usuário.
- **Experiência do Usuário:** Buscar o mínimo impacto na experiência do usuário, lembrando que menos visuais geralmente resultam em melhor desempenho.
- **Campos no Visual:** Analisar os campos no visual para entender como os detalhes estão sendo representados.

**DAX:**

- **Tempo de Execução da Consulta:** Analisar o tempo de execução de consultas DAX usando o Performance Analyzer para identificar consultas lentas e otimizar o código DAX.
- **Performance Analyzer:** Utilizar a ferramenta Performance Analyzer para monitorar o desempenho das consultas DAX.
- **Referência:** As consultas DAX geralmente levam em torno de 120 milissegundos para serem executadas. Se uma consulta DAX leva mais tempo do que o esperado, é sinal de que pode haver um problema de desempenho.

**Modelo de Dados:**

- **Visuais com bom Desempenho:** Verificar se os visuais estão funcionando com bom desempenho, indicando um modelo de dados eficiente.
- **DAX com Execução Rápida:** Consultas DAX com execução rápida indicam um modelo de dados bem estruturado.
- **Possíveis Problemas:** Observar se as relações, colunas ou metadados no modelo de dados estão causando gargalos de desempenho.

**Pontos de Atenção:**

- **Relações e Cardinalidade:** Verificar as relações e cardinalidades no modelo de dados para identificar possíveis gargalos.
- **Colunas Desnecessárias:** Eliminar colunas desnecessárias do modelo de dados para reduzir o tamanho do arquivo.
- **Preferência de Exclusão:** Preferir a exclusão de colunas desnecessárias na importação para evitar a inclusão de dados desnecessários.
- **Power Query:** Utilizar o Power Query para realizar a reestruturação de dados quando necessário.

**Técnicas para Redução de Dados:**

- **Remover Colunas Desnecessárias:** Eliminar colunas que não são utilizadas no relatório.
- **Remover Linhas Desnecessárias:** Excluir linhas que não são relevantes para a análise.
- **Otimizar Tipos de Dados:** Utilizar o tipo de dado adequado para cada coluna, otimizando o armazenamento.
- **Colunas Personalizadas:** Criar colunas personalizadas para armazenar cálculos complexos, evitando a repetição de cálculos no DAX.
- **Desabilitar Data/Hora Automática:** Desabilitar a adição automática de data e hora para reduzir o tamanho do arquivo.

**Documentação Oficial:**

- Consulte a documentação oficial do Power BI para obter informações detalhadas sobre as técnicas de otimização de desempenho.

**Objetivo:**

- Mostrar como otimizar os visuais, o código DAX e o modelo de dados para melhorar o desempenho dos relatórios.
- Destacar a importância de analisar o desempenho do relatório e o modelo de dados para garantir uma experiência positiva para o usuário.

**Conclusão:**

A otimização de desempenho é fundamental para garantir a eficiência e o sucesso da BI. As técnicas apresentadas nesta aula podem ajudar a solucionar problemas de desempenho e maximizar o valor da BI dentro de uma organização.

