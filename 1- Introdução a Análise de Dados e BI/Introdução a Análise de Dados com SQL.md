# Introdução a Análise de Dados com SQL

### Aula 1 - Considerações sobre SQL – Ferramenta de todo BI Analyst

**Introdução à análise de dados com SQL:**

- **História e conceitos:**
    - SQL é uma linguagem de consulta a bancos de dados, surgida na década de 1970.
    - Importância de conhecer o contexto histórico da linguagem para entender sua evolução e adaptação às demandas da área.
- **Estrutura de um banco de dados relacional:**
    - A estrutura de um banco de dados relacional é bem definida, organizada em tabelas com restrições, tipos de dados e constraints.
    - **Exemplo:**
        
        ```sql
        CREATE TABLE customers (
            customer_id INT PRIMARY KEY,
            first_name VARCHAR(255),
            last_name VARCHAR(255),
            email VARCHAR(255),
            phone VARCHAR(20)
        );
        
        ```
        
- **Tipos de análises:**
    - A análise de dados com SQL pode ser descritiva (caracterizar), diagnóstica (entender o porquê), preditiva (analisar o que pode acontecer) e prescritiva (prescrever uma solução).
    - **Exemplos:**
        - **Analítica descritiva:**
            
            ```sql
            SELECT COUNT(*) AS total_customers
            FROM customers;
            
            ```
            
        - **Analítica diagnóstica:**
            
            ```sql
            SELECT  product_name, SUM(quantity) AS total_sold
            FROM orders
            GROUP BY product_name
            HAVING SUM(quantity) > 100;
            
            ```
            
- **Classificações do SQL:**
    - DDL (Data Definition Language): Define a estrutura do banco de dados.
    - DML (Data Manipulation Language): Permite a manipulação de dados.
    - DCL (Data Control Language): Gerencia o controle de acesso ao banco de dados.
    - DQL (Data Query Language): Permite a consulta de dados.
- **SQL Analytics:**
    - SQL Analytics é uma técnica que utiliza o SQL para extrair insights relevantes para a tomada de decisões em Business Intelligence.

**Vantagens do SQL para BI:**

- **Potência computacional:**
    - O SQL é capaz de lidar com grandes volumes de dados de forma rápida e eficiente.
- **Técnicas estatísticas:**
    - O SQL oferece diversas funções estatísticas para cálculos e análises.
    - **Exemplo:**
        
        ```sql
        SELECT AVG(salary) AS average_salary
        FROM employees;
        
        ```
        
- **Técnicas avançadas de machine learning:**
    - A linguagem pode ser utilizada com machine learning, abrindo novas possibilidades de análise.
- **Abordagem abstrata dos dados:**
    - O SQL permite trabalhar com dados de forma abstrata, sem se preocupar com a estrutura física do banco de dados.
- **Facilidade de uso e intuição:**
    - O SQL é relativamente fácil de aprender e usar, tornando-o uma ferramenta acessível para diversas pessoas.
- **Grande parte dos dados do mundo já está em bancos de dados relacionais:**
    - A alta prevalência de SGBDs torna o SQL uma ferramenta essencial para a análise de dados em diversos setores.

**Desafios da análise de dados:**

- **Custo e valor:**
    - É importante considerar o custo de implementação e manutenção de um sistema de análise de dados.
    - A análise de dados deve trazer valor para a empresa, justificando o investimento.
- **Ética na análise de dados:**
    - É crucial garantir a ética e a segurança no manuseio de dados, principalmente dados pessoais e sensíveis.
    - As questões éticas devem ser consideradas durante todo o processo de análise.
- **Segurança dos dados:**
    - A segurança dos dados é fundamental para garantir a integridade e confidencialidade das informações.
    - O SQL deve ser utilizado com cuidado e segurança para proteger os dados.

**Workflow da análise de dados:**

- **Criar um cenário do mundo real:**
    - Para realizar a análise com SQL, é necessário criar um cenário real e relevante para o contexto da empresa.
    - A definição do cenário ajuda a direcionar a análise e a interpretação dos resultados.
- **Definir o problema:**
    - O problema a ser analisado deve ser claramente definido e delimitado.
    - É importante entender o que se deseja descobrir com a análise.
- **Analisar o problema:**
    - Com base no problema definido, utiliza-se o SQL para extrair insights dos dados e realizar a análise.
    - A análise deve ser estruturada e lógica, utilizando as ferramentas do SQL de forma eficiente.
- **Definir a solução:**
    - Após a análise, os resultados devem ser interpretados para identificar possíveis soluções para o problema.
    - A tomada de decisão deve ser baseada nos insights obtidos com a análise dos dados.

**Tipos de análises:**

- **Analítica descritiva:**
    - O objetivo da análise descritiva é caracterizar os dados, utilizando funções de agregação como soma, máximo, mínimo, média, contagem, etc.
    - **Exemplo:**
        
        ```sql
        SELECT SUM(sales) AS total_sales
        FROM orders
        WHERE order_date BETWEEN '2023-01-01' AND '2023-03-31';
        
        ```
        
- **Analítica diagnóstica:**
    - A análise diagnóstica busca entender o porquê de determinada situação, explorando as causas e relacionamentos entre os dados.
    - **Exemplo:**
        
        ```sql
        SELECT  customer_id, COUNT(*) AS number_of_orders
        FROM orders
        GROUP BY customer_id
        ORDER BY number_of_orders DESC;
        
        ```
        
- **Analítica preditiva:**
    - O intuito da análise preditiva é analisar o que pode acontecer, utilizando técnicas de machine learning e algoritmos para prever cenários futuros.
    - **Exemplo:**
        
        ```sql
        -- A análise preditiva normalmente utiliza algoritmos complexos que exigem ferramentas especializadas além do SQL.
        -- Este exemplo é apenas ilustrativo, mostrando a aplicação de uma função de previsão em SQL.
        SELECT  order_date, PREDICT(sales, 7) AS predicted_sales
        FROM orders
        ORDER BY order_date;
        
        ```
        
- **Analítica prescritiva:**
    - A análise prescritiva vai além da previsão, indicando ações e soluções para determinado problema.
    - **Exemplo:**
        
        ```sql
        -- A análise prescritiva normalmente utiliza algoritmos complexos que exigem ferramentas especializadas além do SQL.
        -- Este exemplo é apenas ilustrativo, mostrando a aplicação de uma função de otimização em SQL.
        SELECT  product_id, OPTIMIZE(inventory, 7) AS optimal_inventory
        FROM products
        ORDER BY product_id;
        
        ```
        

### Aula 2 - **Workbench e DBeaver - Explorando Ferramentas de Acesso à Banco de Dados**

- **Workbench:**
    - Uma ferramenta gráfica popular para trabalhar com MySQL.
    - Permite criar, editar e executar scripts SQL.
    - Oferece recursos como:
        - Visualização de tabelas e dados.
        - Editor de consultas (queries) com autocompletar.
        - Recursos de debug.
        - Gerenciamento de conexões e usuários.
    - **Exemplo:**
        
        ```sql
        SELECT *
        FROM customers;
        
        ```
        
- **DBeaver:**
    - Uma ferramenta de código aberto que oferece suporte a diversas plataformas de bancos de dados.
    - Além das funcionalidades do Workbench, o DBeaver:
        - Oferece suporte a bancos de dados relacionais e NoSQL.
        - Permite criar diagramas de entidade-relacionamento (ERD).
        - Visualizar e editar metadados do banco de dados.
        - Exportar dados em diferentes formatos (CSV, JSON, XML, etc.).
    - **Exemplo:**
        
        ```sql
        SELECT  customer_name, COUNT(*) AS number_of_orders
        FROM orders
        GROUP BY customer_name;
        
        ```
        

**Vantagens de Workbench e DBeaver:**

- **Interface gráfica intuitiva:** facilitam o trabalho de manipulação e consulta de dados, mesmo para iniciantes.
- **Diversos recursos:** oferecem funcionalidades para diversas necessidades, como debug, gerenciamento de conexões, criação de diagramas, etc.
- **Flexibilidade:** suportam diversos tipos de bancos de dados e sistemas.

**Links:**

- **Workbench:** https://www.mysql.com/products/workbench/
- **DBeaver:** https://dbeaver.io/

### Aula 3 - **Analisando a Sample do DBeaver persistida no SQlite**

**Utilizando DBeaver para análise de dados:**

- **DBeaver como ferramenta:**
    - DBeaver é uma ferramenta de código aberto que suporta diversos tipos de bancos de dados, inclusive SQLite.
    - Oferece interface gráfica intuitiva para trabalhar com SQL, criar diagramas, visualizar metadados e exportar dados.

**Análise descritiva com SQL:**

- **Exemplos de queries para análise descritiva:**
    - **Verificando o número total de registros em uma tabela:**
        
        ```sql
        SELECT COUNT(*) AS total_albums
        FROM album;
        
        ```
        
    - **Recuperando o ID e o título de todos os álbuns:**
        
        ```sql
        SELECT AlbumId, Title
        FROM album;
        
        ```
        
    - **Recuperando o ID e o título dos álbuns que não possuem artista associado:**
        
        ```sql
        SELECT AlbumId, Title
        FROM album
        WHERE ArtistId IS NULL;
        
        ```
        
    - **Contagem de registros para cada artista:**
        
        ```sql
        SELECT ArtistId, COUNT(*) AS total_albums
        FROM album
        GROUP BY ArtistId;
        
        ```
        
    - **Contagem de registros para cada artista, ordenado pela quantidade de álbuns:**
        
        ```sql
        SELECT ArtistId, COUNT(*) AS total_albums
        FROM album
        GROUP BY ArtistId
        ORDER BY total_albums DESC;
        
        ```
        

**Utilizando Joins para análise:**

- **Realizando um JOIN entre as tabelas "album" e "artist" para obter informações sobre álbuns e seus artistas:**
    
    ```sql
    SELECT Album.AlbumId, Album.Title, Artist.Name AS ArtistName
    FROM album
    INNER JOIN artist ON Album.ArtistId = Artist.ArtistId;
    
    ```
    

### Aula 4 - O que fazer em um primeiro contato com base de dados?

**Entendendo o contexto dos dados:**

- **A importância da análise exploratória:**
    - A análise exploratória de dados é crucial para entender o contexto dos dados, sua estrutura e relações.
    - Não se limite a apenas recuperar dados brutos, busque informações mais profundas.
- **DBeaver como ferramenta:**
    - DBeaver é uma ferramenta que ajuda a visualizar e entender o esquema de um banco de dados, mostrando as relações entre tabelas.
    - Essa visualização permite compreender melhor o contexto dos dados e como eles se conectam.
- **Padronização e limpeza de dados:**
    - SQL oferece recursos para padronizar e limpar dados, como "CASE".
    - Tratar dados inconsistentes garante coerência e facilita a análise.
- **Análise descritiva com SQL:**
    - Utilizar queries SQL para analisar dados e gerar insights sobre o conjunto de dados.
    - A aula não se aprofunda em técnicas complexas de análise nesta etapa, mas enfatiza a importância de começar a explorar.
- **ETL (Extração, Transformação e Carregamento):**
    - O processo de ETL é fundamental para preparar dados brutos para análise.
    - A aula menciona o ETL, mas deixa para abordar este processo em outras aulas.

**O objetivo da aula:**

- Mostrar como realizar um primeiro contato com um banco de dados e extrair insights a partir dele.
- Despertar a necessidade de realizar uma análise exploratória de dados, compreendendo o contexto, a estrutura e as relações entre as tabelas.
- Introduzir o DBeaver como uma ferramenta útil para a análise de dados.

### Aula 5 - Análise Descritiva: Caracterizando os Registros dos Artistas

**Analisando a tabela 'Customer' com SQL:**

- **Objetivo:** Obter informações descritivas sobre os clientes na base de dados.
- **Utilizando Queries:**
    - **Contagem total de clientes:**
        
        ```sql
        SELECT COUNT(*) AS total_customers
        FROM customer;
        
        ```
        
    - **Contagem de clientes por estado:**
        
        ```sql
        SELECT State, COUNT(*) AS customer_count
        FROM customer
        GROUP BY State
        ORDER BY customer_count DESC;
        
        ```
        
    - **Contagem de clientes que não possuem empresa associada:**
        
        ```sql
        SELECT COUNT(*) AS customers_without_company
        FROM customer
        WHERE Company IS NULL;
        
        ```
        
    - **Contagem de clientes por estado, ordenando pelo número de clientes:**
        
        ```sql
        SELECT State, COUNT(*) AS customer_count
        FROM customer
        GROUP BY State
        ORDER BY customer_count;
        
        ```
        
    - **Exibindo o primeiro nome e endereço dos clientes:**
        
        ```sql
        SELECT FirstName, Address
        FROM customer;
        
        ```
        

**Pontos chave da aula:**

- A aula demonstra como usar queries SQL simples para obter informações básicas sobre a tabela 'Customer'.
- O instrutor destaca a importância de:
    - Limitar a quantidade de dados exibidos para evitar sobrecarga.
    - Agrupar dados por critérios relevantes, como estado.
    - Ordenar os resultados para facilitar a análise.
- A aula enfatiza o uso da análise descritiva para gerar insights sobre o conjunto de dados, como a localização dos clientes e o número de clientes sem empresa associada.

### Aula 6 - Análise Descritiva: Caracterizando os Registros dos Customers

**Analisando a tabela 'Invoice' com SQL:**

- **Objetivo:** Obter informações descritivas sobre as Faturas na base de dados.
- **Utilizando Queries:**
    - **Verificando se um cliente está associado a uma Fatura:**
        
        ```sql
        SELECT FirstName, LastName, Invoice.InvoiceId
        FROM Customer
        INNER JOIN Invoice ON Customer.CustomerId = Invoice.CustomerId;
        
        ```
        
    - **Comparando as tabelas 'Customer' e 'Employee':**
        
        ```sql
        SELECT FirstName AS CustomerFirstName, LastName AS CustomerLastName, e.FirstName AS EmployeeFirstName, e.LastName AS EmployeeLastName
        FROM Customer c
        INNER JOIN Employee e ON c.FirstName = e.FirstName AND c.LastName = e.LastName;
        
        ```
        

**Pontos chave da aula:**

- A aula demonstra como usar queries SQL para obter informações sobre as Faturas, incluindo a relação entre Faturas e Clientes.
- O instrutor aborda a comparação entre tabelas, utilizando joins para identificar clientes que também são funcionários.
- O instrutor destaca a importância de:
    - Utilizar joins para combinar dados de diferentes tabelas.
    - Criar queries que extraiam informações relevantes para a análise.

### Aula 7 - Análise Descritiva: Caracterizando os Registros de Invoice

**Analisando a tabela 'Invoice' com SQL:**

- **Objetivo:** Obter informações descritivas sobre as Faturas, incluindo a relação com a tabela 'InvoiceLine'.
- **Utilizando Queries:**
    - **Exibindo InvoiceId, CustomerId, InvoiceDate:**
        
        ```sql
        SELECT InvoiceId, CustomerId, InvoiceDate
        FROM Invoice;
        
        ```
        
    - **Agrupando Faturas por InvoiceLineID:**
        
        ```sql
        SELECT InvoiceId, COUNT(*) AS InvoiceLine_count
        FROM InvoiceLine
        GROUP BY InvoiceId;
        
        ```
        
    - **Agrupando Faturas por CustomerID:**
        
        ```sql
        SELECT InvoiceId, COUNT(*) AS InvoiceLine_count
        FROM InvoiceLine
        GROUP BY CustomerId;
        
        ```
        
    - **Realizando um JOIN entre 'Invoice' e 'InvoiceLine':**
        
        ```sql
        SELECT Invoice.InvoiceId, Invoice.InvoiceDate, InvoiceLine.InvoiceLineId
        FROM Invoice
        INNER JOIN InvoiceLine ON Invoice.InvoiceId = InvoiceLine.InvoiceId;
        
        ```
        

**Pontos chave da aula:**

- A aula demonstra como usar queries SQL para obter informações sobre as Faturas, incluindo a relação com a tabela 'InvoiceLine'.
- O instrutor aborda a importância de:
    - Realizar joins entre tabelas para obter informações mais completas.
    - Agrupar dados por diferentes critérios para entender a distribuição dos dados.

### Aula 8 - Utilizando Junções para Caracterizar os Dados

**Trabalhando com junções em SQL:**

- **Objetivo:** Mostrar como utilizar junções em SQL para combinar dados de diferentes tabelas e obter informações mais completas.
- **Cenários de junção:**
    - **Contagem de Faturas por cliente:**
        
        ```sql
        SELECT CustomerId, COUNT(*) AS Invoice_count
        FROM Invoice
        GROUP BY CustomerId;
        
        ```
        
    - **Verificando se um artista está associado a um álbum:**
        
        ```sql
        SELECT Artist.ArtistId, Artist.Name, Album.Title
        FROM Artist
        INNER JOIN Album ON Artist.ArtistId = Album.ArtistId;
        
        ```
        
    - **Comparando dados de 'Employee' e 'Customer':**
        
        ```sql
        SELECT FirstName AS CustomerFirstName, LastName AS CustomerLastName, e.FirstName AS EmployeeFirstName, e.LastName AS EmployeeLastName
        FROM Customer c
        INNER JOIN Employee e ON c.FirstName = e.FirstName AND c.LastName = e.LastName;
        
        ```
        

**Pontos chave da aula:**

- A aula enfatiza a importância de utilizar joins para combinar dados de diferentes tabelas e obter informações mais completas.
- O instrutor demonstra como usar a cláusula "INNER JOIN" para combinar tabelas com base em colunas correspondentes.
- O instrutor explica como realizar consultas que cruzam dados de diferentes tabelas.

### Aula 9 - Analisando Frequência dos Dados com Funções de Agregação

**Conceitos:**

- **Funções de agregação:** São usadas para calcular valores resumidos a partir de conjuntos de dados. Exemplos: COUNT, SUM, AVG, MAX, MIN.

**Cenários de agregação:**

- **Contagem de Employees por departamento:**
    
    ```sql
    SELECT D.Dept_No, D.Dept_Name, COUNT(E.Emp_No) AS Total_Employees
    FROM Dept D
    LEFT JOIN Employees E ON D.Dept_No = E.Dept_No
    GROUP BY D.Dept_No, D.Dept_Name
    ORDER BY D.Dept_No;
    
    ```
    
- **Contagem de projetos por departamento:**
    
    ```sql
    SELECT D.Dept_No, D.Dept_Name, COUNT(P.Proj_No) AS Total_Projects
    FROM Dept D
    LEFT JOIN Project P ON D.Dept_No = P.Dept_No
    GROUP BY D.Dept_No, D.Dept_Name
    ORDER BY D.Dept_No;
    
    ```
    

**Pontos chave da aula:**

- A aula demonstra como aplicar funções de agregação (COUNT) em SQL para analisar a frequência de dados.
- O instrutor mostra como combinar funções de agregação com a cláusula "GROUP BY" para agrupar e analisar dados.
- A aula destaca a importância de usar "GROUP BY" para obter resultados resumidos.
- O instrutor utiliza a função "LEFT JOIN" para combinar tabelas.
- A aula mostra como gerar relatórios de frequência com "ORDER BY".

**Aplicações práticas:**

- A aula fornece exemplos de como a análise de frequência pode ser usada para entender a distribuição de dados em diferentes departamentos.
- O instrutor mostra como obter insights valiosos sobre o número de funcionários e projetos em cada departamento.

### Aula 10 - Discretização com CASE Statement

**Cenários:**

- **Categorização de funcionários por faixa salarial:**
    
    ```sql
    SELECT FirstName, LastName, Salary,
    	CASE
    		WHEN Salary > 60000 THEN 'Senior'
    		WHEN Salary > 40000 AND Salary <= 60000 THEN 'Pleno'
    		ELSE 'Junior'
    		END AS Employee_Level
    		FROM Employees
    		ORDER BY Salary;
    
    ```
    
- **Categorização de clientes por NPS:**
    
    ```sql
    SELECT CustomerId,
    	CASE
    		WHEN NPS > 7 THEN 'Promotor'
    		WHEN NPS < 7 AND NPS >= 0 THEN 'Detrator'
    		ELSE 'Passivo'
    		END AS NPS_Category
    		FROM Customer
    		ORDER BY NPS;
    
    ```
    

**Pontos chave da aula:**

- A aula explica como o CASE Statement é uma ferramenta poderosa para categorizar dados contínuos em bins.
- O instrutor demonstra a sintaxe e a lógica do CASE Statement.
- O instrutor demonstra como usar o CASE Statement para categorizar funcionários por níveis salariais e clientes por NPS.
- A aula destaca o uso de "ORDER BY" para organizar os resultados.

**Aplicações práticas:**

- A aula fornece exemplos de como o CASE Statement pode ser usado para segmentar clientes, analisar o desempenho de funcionários, e outros cenários de negócios.

### Aula 11 - Aplicando Padronização na Recuparação dos Dados com CASE Statement

**Cenários:**

- **Padronização de gêneros em uma tabela:**
    
    ```sql
    SELECT FirstName, LastName,
    CASE
    WHEN Gender = 'M' THEN 'Masculino'
    WHEN Gender = 'F' THEN 'Feminino'
    ELSE 'Outro'
    END AS Gender_Description
    FROM Employees;
    
    ```
    
- **Cálculo de indicadores com padronização de dados:**
    
    ```sql
    SELECT D.Dept_Name,
    COUNT(E.Emp_No) AS Total_Employees,
    SUM(CASE WHEN E.Salary > 60000 THEN 1 ELSE 0 END) AS Senior_Employees,
    SUM(CASE WHEN E.Salary > 40000 AND E.Salary <= 60000 THEN 1 ELSE 0 END) AS Pleno_Employees
    FROM Dept D
    LEFT JOIN Employees E ON D.Dept_No = E.Dept_No
    GROUP BY D.Dept_Name
    ORDER BY D.Dept_Name;
    
    ```
    

**Pontos chave da aula:**

- A aula demonstra como usar o CASE Statement para padronizar dados, tornando-os mais legíveis e consistentes.
- O instrutor mostra como integrar o CASE Statement com outras instruções SQL para manipular dados.
- A aula destaca a importância da padronização de dados para análise e relatórios.
- O instrutor utiliza a função "SUM" para calcular indicadores.

**Aplicações práticas:**

- A aula fornece exemplos de como a padronização de dados pode ser usada para melhorar a qualidade de dados e simplificar análises.
- O instrutor mostra como combinar CASE Statement com outros elementos do SQL para realizar tarefas complexas de análise.

**Observações:**

O código da aula:

```sql
SELECT * FROM Album a ;
SELECT count(*) AS Records FROM Album a;

SELECT count(*) FROM Album a WHERE Column1 is NOT NULL;
SELECT AlbumId, Title FROM Album a WHERE Column1 is NULL;

SELECT * FROM Artist a;

-- caracterizando os registros dos artistas
SELECT a2.ArtistId, a2.Name, count(*) AS Records FROM Album a INNER JOIN Artist a2 GROUP BY 1;
SELECT a2.ArtistId, a2.Name, count(*) AS Records FROM Album a INNER JOIN Artist a2 GROUP BY 1 ORDER BY Records LIMIT 3;

SELECT * FROM Customer c LIMIT 10;
SELECT COUNT(*) FROM Customer c2 ;
SELECT FirstName, Address FROM Customer c;

-- Quantos clientes moram na Broadway?
SELECT count(*) FROM Customer c WHERE Address like '%Broadway%';
SELECT State, COUNT(*) AS Total FROM Customer c GROUP BY 1 ORDER BY Total DESC LIMIT 10;

-- verificar company dos clientes
SELECT * FROM Customer c;
SELECT count(*) FROM Customer c WHERE Company IS NOT NULL;

SELECT FirstName FROM Customer c WHERE Company IS NULL;

-- Quais dos clientes são colaboradores?
SELECT * FROM Employee e ;

SELECT c.FirstName, c.LastName FROM Customer c 
	WHERE Company IS NULL AND c.FirstName IN 
		(SELECT e.FirstName FROM Employee e);

SELECT c.FirstName, c.LastName  FROM Customer c INNER JOIN Employee e WHERE c.FirstName = e.FirstName;

SELECT * FROM Invoice i LIMIT 10;
SELECT * FROM InvoiceLine il ORDER BY UnitPrice  DESC LIMIT 10;

SELECT UnitPrice, COUNT(*) AS Record  FROM InvoiceLine il GROUP BY UnitPrice;

-- Clientes que possuem Invoice associados e a quantidade para cada cliente.

SELECT c.CustomerId, c.FirstName, COUNT(*) AS Record FROM Invoice i 
	INNER JOIN Customer c ON c.CustomerId = i.CustomerId 
	GROUP BY 1 ORDER BY Record;

SELECT i.InvoiceId, il.InvoiceLineId  FROM Invoice i 
	INNER JOIN InvoiceLine il 
	INNER JOIN Customer c ON c.CustomerId = i.CustomerId 
	GROUP BY 1
	LIMIT 100;
```

### Materiais Complementares

[Curso 2 - Introdução a Análise de Dados com SQL.pdf](https://prod-files-secure.s3.us-west-2.amazonaws.com/5f9b2a52-e80e-40bf-9263-c2b21d7b302c/650e4c5f-8594-410c-ab06-3827643c7cd0/Curso_2_-_Introduo_a_Anlise_de_Dados_com_SQL.pdf)

https://github.com/julianazanelatto/power_bi_analyst
