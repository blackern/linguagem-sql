# 1. Introdução ao SQL

- **O que é SQL:** SQL significa Linguagem de Consulta Estruturada e frequentemente é pronunciada como SeQuel.
- **Para que o SQL serve?** É usada para interagir com dados armazenados em bancos de dados, permitindo fazer cálculos complexos e encontrar informações em grandes conjuntos de dados.
- **Porque aprender SQL?** Permite comunicar diretamente com sistemas de dados e possui uma alta demanda no mercado para diversas funções técnicas como Desenvolvedor, Analista, Cientista e Engenheiro de Dados, além de ser o padrão da indústria utilizado em ferramentas como Power BI, Tableau, Kafka, Spark e Synapse.

# 2. Sistema de Gerenciamento de Banco de Dados (DBMS)

- Um DBMS atua como interface entre o usuário e o banco de dados.
- Os bancos de dados normalmente são hospedados em um servidor ou na nuvem, e esses sistemas geralmente funcionam 24/7 para garantir que os dados estejam sempre acessíveis.
- Aplicativos (APP </>) e ferramentas de BI (Power BI) enviam consultas SQL com o objetivo de gerenciar e recuperar dados no DBMS.

## Tipos de Bancos de Dados

- **Relacional:** Por exemplo: Microsoft SQL Server, MySQL, PostgreSQL e Amazon Redshift.
- **Documento:** Por exemplo: MongoDB.
- **Grafo:** Por exemplo: Neo4j.
- **Chave-Valor:** Por exemplo: Redis e Amazon DynamoDB.
- **Base de Coluna:** Por exemplo: Apache Cassandra (GitHub).

# 3. Estrutura de Banco de Dados e Componentes de uma Tabela

Bancos de dados relacionais seguem uma organização hierárquica:

- **Servidor:** O host principal contendo um ou mais bancos de dados.
- **Banco de Dados:** Contêiner de alto nível para dados, como “Vendas” ou “RH”.
- **Esquema:** Agrupamentos lógicos dentro de um banco de dados, como “Pedidos” ou “Clientes”.
- **Tabela:** Onde os dados são fisicamente armazenados em linhas e colunas.
- **Colunas:** Categorias verticais definindo tipos de dados.
- **Linhas:** Registros horizontais individuais.
- **Célula:** Uma unidade única de dado na interseção de linha e coluna.
- **Chave Primária:** Identificador único para cada registro em uma tabela.
- **Armazenamento:** Tabelas são armazenadas como arquivos de banco de dados em disco físico.

## Tipos de Dados

- **Numéricos:** INT (Números inteiros) e DECIMAL (Valores numéricos com frações).
- **Texto/String:** CHAR (Strings de comprimento fixo) e VARCHAR (Strings de comprimento variável).
- **Data & Hora:** DATE (Formato 'YYYY-MM-DD') e TIME (Formato 'HH:MM:SS').

# 4. Os Tipos de Comandos SQL

O SQL se divide em cinco "famílias" funcionais, cada uma com uma responsabilidade distinta sobre o ecossistema de dados.

- **DDL (Linguagem de Definição de Dados):** Usado para definir ou modificar a estrutura do banco de dados (CREATE, ALTER, DROP).
- **DQL (Linguagem de Consulta de Dados):** Usado para recuperar dados do banco de dados (SELECT).
- **DML (Linguagem de Manipulação de Dados):** Usado para gerenciar dados dentro das tabelas (INSERT, UPDATE, DELETE).
- **DCL (Linguagem de Controle de Dados):** Usado para gerenciar permissões e controle de acesso. (GRANT, REVOKE).
- **TCL (Linguagem de Controle de Transações):** Usado para gerenciar transações no banco de dados (COMMIT, ROLLBACK, SAVEPOINT).

# 5. DDL - Linguagem de Definição de Dados

A DDL (Linguagem de Definição de Dados) é a linguagem utilizada para definir a estrutura dos nossos objetos de dados, funcionando como o "esqueleto" ou a planta estrutural (blueprint) do banco de dados. Enquanto a DQL consulta e a DML manipula, a DDL gerencia o contêiner onde as informações residem através de três ações principais:

- **CREATE:** Usado para construir novos objetos, como Bancos de Dados ou Tabelas, do zero.
- **ALTER:** Utilizado para modificar a estrutura de um objeto que já existe, como adicionar ou remover colunas.
- **DROP:** Comando destrutivo usado para excluir permanentemente um objeto e todos os registros contidos nele.

# 6. DML - Linguagem de Manipulação de Dados

Enquanto a DDL define o "recipiente" (a estrutura), a DML (Linguagem de Manipulação de Dados) é utilizada para gerenciar o conteúdo interno das tabelas. Ela permite alterar os dados reais armazenados através de três operações primárias:

- **INSERT:** Adiciona novas linhas de dados a uma tabela.
- **UPDATE:** Modifica informações que já existem dentro de uma tabela.
- **DELETE:** Remove registros específicos que não são mais necessários.

# 7. DQL - Linguagem de Consulta de Dados

A DQL (Linguagem de Consulta de Dados) é a parte da linguagem focada em extrair informações do banco de dados. O comando principal é o SELECT, que funciona como uma lente para visualizar os dados armazenados.

## Anatomia de uma Instrução SQL

Uma consulta SQL não é apenas texto, ela é composta por elementos específicos que instruem o banco sobre como processar o pedido:

- **Comentários (--):** Documentam o código para leitura humana.
- **Palavras-chave:** Termos reservados com significado especial para o motor SQL.
- **Cláusulas:** Os blocos fundamentais que constroem a instrução (ex: SELECT, FROM).
- **Identificadores:** Nomes de objetos, como tabelas ou colunas.
- **Operadores e Literais:** Usados para comparações e valores constantes, respectivamente.
- **Funções:** Ferramentas que transformam os dados durante a consulta.

## Estrutura Basica

```SELECT column_name FROM table_name;```

## Filtragem e Organização

- **WHERE:** Filtra registros baseando-se em condições específicas.
- **ORDER BY:** Ordena os resultados de forma ascendente ou descendente.
- **DISTINCT:** Remove linhas duplicadas do resultado final.
- **TOP / LIMIT:** Restringe a quantidade de registros retornados.
- **Aliases (AS):** Define nomes temporários para colunas ou tabelas, facilitando a leitura.

## A Ordem Lógica de Processamento

Um ponto crucial para desenvolvedores é entender que o SQL não processa as cláusulas na ordem em que são escritas. Para evitar erros de lógica, lembre-se da execução padrão:

1. **FROM:** Primeiro, o banco identifica a origem dos dados (a tabela).
2. **WHERE:** Em seguida, aplica os filtros para reduzir o volume de dados.
3. **SELECT:** Só então ele seleciona as colunas solicitadas.
4. **ORDER BY:** Por fim, organiza o resultado para exibição.

# 8. Chave Estrangeira

- **O que é uma Chave Estrangeira (Foreign Key)?** A chave estrangeira é um campo de uma tabela que aponta para a chave primária de outra tabela.

- **Para que a Chave Estrangeira serve?** Ela serve para criar relacionamentos entre tabelas, em outras palavras a chave estrangeira é o que "liga" uma tabela à outra em um banco de dados relacional.

## Porque precisamos delas?

**Sem chave estrangeira:**
- As tabelas ficam isoladas
- Não há garantia de que os dados combinam
- Podem existir registros "órfãos" (sem relação real)

**Com chave estrangeira:**
- O banco garante integridade dos dados
- Evita erros e inconsistências
- Representa relações do mundo real (cliente → pedido, aluno → matrícula, etc.) 

# 9. Normalização

Normalizar um banco de dados é organizar as informações para que cada dado exista apenas uma vez, evitando repetição, erros e bagunça nas tabelas.

## Por que precisamos normalizar?

**Sem Normalização (Forma Não Normalizada - UNF):**
- Todos os dados estão misturados em uma única tabela, com grupos repetidos.
- Dados do cliente repetidos.
- Difícil de consultar e manter.

**Com Normalização (Resultado):**
- Ausência de redundância.
- Relacionamentos claros (Chaves Estrangeiras).
- Estrutura relacional correta e melhor desempenho.
- Manutenção facilitada.

## As Três Formas Normais

### 1. Primeira Forma Normal (1FN)
- **Regra:** Os campos devem ser atômicos (um único valor por célula).
- **O que acontece:** Resolve o problema de grupos repetidos, mas os dados do cliente continuam duplicados.
- **Observação:** O Total pertence APENAS ao pedido.

### 2. Segunda Forma Normal (2FN)
- **Regras:** Deve estar na 1FN e remover as dependências parciais.
- **O que acontece:** Cada entidade passa a ter sua própria tabela e ter sua própria chave primária.
- **Observação:** O Produto ainda é um texto livre... está "solto".

### 3. Terceira Forma Normal (3FN)
- **Regras:** Deve estar na 2FN e remover dependências transitivas.
- **O que acontece:** Campos não-chave DEVEM depender apenas da chave.
- **Resultado:** O banco torna-se mais eficiente, confiável e fácil de escalar e entender.

# 10. Métodos de Combinação

Existem duas formas principais de combinar dados no SQL: a adição de colunas (horizontal) e a adição de linhas (vertical).

## JOINS (Adição de Colunas - Horizontal)

Conectamos tabelas lateralmente através de uma coluna comum, chamada de Chave.

- **Inner Join:** Retorna apenas o que existe em ambas as tabelas.
- **Left Join:** Mantemos tudo da tabela à esquerda e trazemos o que houver correspondente na direita.
- **Right Join:** Mantemos tudo da tabela à direita e trazemos o que houver correspondente na esquerda.
- **Full Join:** Trazemos tudo de ambos os lados, independentemente de haver correspondência.

## Como Usamos Joins

Ao escrevermos um JOIN, devemos especificar a relação:

```sql
SELECT
    TabelaA.Nome,
    TabelaB.Pais
FROM
    TabelaA INNER JOIN TabelaB ON TabelaA.id = TabelaB.id;
```

## Operadores SET (Adição de Linhas - Vertical)

Empilhamos resultados de consultas diferentes, desde que tenham a mesma estrutura de colunas.

- **UNION:** Combina os resultados de duas consultas e remove registros duplicados.
- **UNION ALL:** Combina tudo de ambas as consultas, incluindo os duplicados, sendo um método mais rápido.
- **EXCEPT / MINUS:** Mostra apenas o que existe no primeiro conjunto de dados, mas não no segundo.
- **INTERSECT:** Mostra apenas o que é comum (exatamente igual) a ambos os conjuntos.

## Como Usamos Set

Ao escrevermos um SET, devemos especificar a relação:

```sql
SELECT
    Nome
FROM
    Clientes
UNION
SELECT
    Nome
FROM
    Funcionarios;
```

## Porque precisamos deles?

**Com JOINS:**
- Conseguimos relacionar informações de entidades diferentes (ex: Cliente e Pais) em uma mesma linha.
- O banco mantém sua estrutura normalizada, mas permite visualização integrada.

**Com Operadores SET:**
- Permite unificar listas de origens diferentes (ex: Clientes e Funcionários) em uma única coluna.
- Facilita comparações entre conjuntos de dados para encontrar diferenças ou semelhanças.

# 11. Linguagem SQL - Funções de Linha Única no SQL

Conjuntos de instruções que recebem um ou mais valores de entrada e retornam um valor de saída.

## Quais são suas utilidades e seu processo?

- **Limpeza:** Remover espaços extras ou caracteres indesejados. 
- **Transformação:** Alterar formatos de data ou converter textos.
- **Análise:** Realizar cálculos rápidos por linha.
- **Processo:** Entrada (Valor) -> FUNÇÃO -> Saída (Novo Valor)

## Funções de Texto (String Functions)

**Manipulação:**
- CONCAT: Une duas ou mais strings (ex: Nome + Sobrenome).
- UPPER / LOWER: Converte o texto para MAIÚSCULO ou minúsculo.
- TRIM: Remove espaços em branco no início e no fim.
- REPLACE: Substitui um caractere ou trecho de texto por outro.

**Extração e Medida:**
- LEN: Retorna a quantidade de caracteres.
- LEFT / RIGHT: Extrai caracteres a partir da esquerda ou direita.
- SUBSTRING: Extrai uma parte específica do texto de qualquer posição.

## Funções de Data e Hora (Date & Time)

**Cálculos:**
- DATEADD: Adiciona um intervalo (dias, meses, anos) a uma data.
- DATEDIFF: Calcula a diferença entre duas datas.

**Extração de Partes:**
- YEAR, MONTH, DAY: Extraem o ano, mês ou dia numérico.
- DATENAME: Retorna o nome da parte da data (ex: "Janeiro", "Segunda-feira").

**Conversão:**
- CAST / CONVERT: Alteram o tipo de dado (ex: de Texto para Data).
- FORMAT: Define como a data será exibida (ex: 'dd/MM/yyyy').

## Tratamento de Valores Nulos (NULL Functions)

Por que tratar nulos? Evitar erros em cálculos e garantir relatórios precisos

**Principais Funções:**
- ISNULL(valor, substituto): Se o valor for nulo, substitui por outro.
- COALESCE(v1, v2, ...): Retorna o primeiro valor não nulo de uma lista.
- NULLIF(v1, v2): Retorna nulo se os dois valores forem iguais.
- IS NULL: Operador para filtrar registros sem dados.

## Lógica Condicional (CASE Statement)

O que é: Funciona como um "SE... ENTÃO" (IF... THEN) dentro do SQL.

**Aplicações:**
- Categorização: Se Venda > 1000 então 'Premium'.
- Padronização: Converter 'Alemanha' para 'DE', 'Brasil' para 'BR'.

**Sintaxe Básica:**
```sql
CASE
    WHEN Condição THEN Resultado
    ELSE Resultado_Padrão
END
```

## Funções Aninhadas (Nested Functions)

Usar uma função como entrada para outra função.

**Exemplo Prático:**
- LEN(LOWER(LEFT('Maria', 2)))
- LEFT('Maria', 2) -> 'Ma'
- LOWER('Ma') -> 'ma'
- LEN('ma') -> Resultado Final: 2

# 12. Linguagem SQL - Funções de Agregação

As funções de agregação processam um conjunto de valores para retornar um único valor resumido. Elas são essenciais para transformar dados brutos em informações estratégicas.

- **COUNT:** Conta registros.
- **SUM / AVG:** Soma e média (apenas numéricos).
- **MAX / MIN:** Valores máximo e mínimo.

# Cláusula GROUP BY (Agrupamento)

A cláusula GROUP BY é utilizada para organizar linhas que possuem valores idênticos em grupos. Ela é quase sempre utilizada em conjunto com as funções de agregação mencionadas acima.

**Condensação de Registros:** A principal função do GROUP BY é reduzir (achatar) múltiplos registros em uma única linha de resumo por grupo.

**Cálculos em Nível de Grupo:** Ao contrário de uma conta simples no banco de dados inteiro, o agrupamento permite realizar Cálculos de Nível de Grupo (ex: calcular o faturamento total por categoria de produto em vez do faturamento total da loja).

# 13. Views

Uma **View** é um objeto do banco de dados que funciona como uma tabela virtual. Ela é criada a partir de uma instrução `SELECT` e, normalmente, não armazena os dados fisicamente, apenas exibe o resultado da consulta.

## Benefícios

- Facilita consultas complexas.
- Restringe o acesso direto às tabelas.
- Permite reutilizar consultas frequentemente utilizadas.
- Melhora a organização do banco de dados.

## Exemplo de Criação

```sql
CREATE VIEW vw_ClientesAtivos AS
SELECT
    Id,
    Nome,
    Email
FROM Clientes
WHERE Ativo = 1;
```

## Utilização

```sql
SELECT * FROM vw_ClientesAtivos;
```

# 14. Functions

As **Functions** são rotinas criadas para executar operações específicas. Elas podem receber parâmetros e obrigatoriamente retornam um valor ou conjunto de registros.

## Principais Características

- Permitem reutilização de código.
- Possuem retorno obrigatório.
- Podem ser utilizadas em consultas SQL.
- Auxiliam na padronização de cálculos e regras.

## Exemplo

```sql
CREATE FUNCTION fn_CalcularDesconto
(
    @Valor DECIMAL(10,2)
)
RETURNS DECIMAL(10,2)
AS
BEGIN
    RETURN @Valor * 0.9;
END;
```

## Chamada da Function

```sql
SELECT dbo.fn_CalcularDesconto(1000);
```

# 15. Stored Procedures

As **Stored Procedures** são procedimentos armazenados diretamente no banco de dados. Elas podem conter uma ou várias instruções SQL que serão executadas quando chamadas.

## Vantagens

- Redução da duplicação de código.
- Melhor desempenho em determinadas operações.
- Centralização das regras de negócio.
- Facilidade de manutenção.

## Exemplo

```sql
CREATE PROCEDURE sp_ListarClientes
AS
BEGIN
    SELECT *
    FROM Clientes;
END;
```

## Execução

```sql
EXEC sp_ListarClientes;
```

# 16. Triggers

As **Triggers** são rotinas executadas automaticamente quando ocorre um evento em uma tabela ou visão.

## Eventos que Podem Disparar uma Trigger

- `INSERT`
- `UPDATE`
- `DELETE`

## Casos de Uso

- Registro de auditoria.
- Criação de logs.
- Aplicação de regras de negócio.
- Monitoramento de alterações.

## Exemplo

```sql
CREATE TRIGGER trg_LogClientes
ON Clientes
AFTER INSERT
AS
BEGIN
    PRINT 'Cliente inserido com sucesso';
END;
```

# 17. DCL (Data Control Language)

A **DCL** é responsável por administrar permissões e controlar o acesso aos objetos do banco de dados.

## Comandos Mais Utilizados

### GRANT

Concede permissões a usuários ou grupos.

```sql
GRANT SELECT
ON Clientes
TO UsuarioAnalista;
```

### REVOKE

Remove permissões previamente concedidas.

```sql
REVOKE SELECT
ON Clientes
FROM UsuarioAnalista;
```

## Finalidade

Garantir que apenas usuários autorizados possam consultar ou modificar determinadas informações.

# 18. TCL (Transaction Control Language)

A **TCL** gerencia transações, permitindo controlar quando alterações devem ser confirmadas ou desfeitas.

## O que é uma Transação?

Uma transação representa um conjunto de operações executadas como uma única unidade lógica. Caso ocorra algum problema, é possível desfazer todas as alterações realizadas.

## Principais Comandos

| Comando | Descrição |
|----------|----------|
| BEGIN TRANSACTION | Inicia uma transação |
| COMMIT | Salva definitivamente as alterações |
| ROLLBACK | Cancela as alterações realizadas |
| SAVEPOINT | Cria um ponto de retorno dentro da transação |

## Exemplo de Transação

```sql
BEGIN TRANSACTION;

UPDATE Contas
SET Saldo = Saldo - 100
WHERE Id = 1;

UPDATE Contas
SET Saldo = Saldo + 100
WHERE Id = 2;

COMMIT;
```

## Exemplo Utilizando ROLLBACK

```sql
BEGIN TRANSACTION;

UPDATE Produtos
SET Estoque = Estoque - 10
WHERE Id = 1;

ROLLBACK;
```

## Relação com o Conceito ACID

As transações garantem as propriedades ACID:

- **Atomicidade:** a operação é executada integralmente ou não é executada.
- **Consistência:** os dados permanecem válidos após a transação.
- **Isolamento:** transações simultâneas não interferem entre si.
- **Durabilidade:** alterações confirmadas permanecem registradas.

# 19. Resumo das Categorias SQL

### DDL (Data Definition Language)

Utilizada para criar, alterar e remover estruturas do banco de dados.

**Principais comandos:** `CREATE`, `ALTER`, `DROP`.

### DML (Data Manipulation Language)

Responsável pela manipulação dos dados armazenados nas tabelas.

**Principais comandos:** `INSERT`, `UPDATE`, `DELETE`.

### DQL (Data Query Language)

Empregada para realizar consultas e recuperar informações do banco de dados.

**Principal comando:** `SELECT`.

### DCL (Data Control Language)

Utilizada para controlar permissões e definir quais usuários podem acessar determinados recursos.

**Principais comandos:** `GRANT`, `REVOKE`.

### TCL (Transaction Control Language)

Responsável pelo gerenciamento de transações, garantindo a integridade dos dados.

**Principais comandos:** `BEGIN TRANSACTION`, `COMMIT`, `ROLLBACK`, `SAVEPOINT`.

# Considerações Finais

- A **DDL** é utilizada para criar e modificar estruturas.
- A **DML** permite inserir, alterar e excluir dados.
- A **DQL** é voltada para consultas.
- A **DCL** controla o acesso aos recursos do banco.
- A **TCL** assegura a integridade das transações.
- **Views** simplificam consultas e aumentam a segurança.
- **Functions** encapsulam cálculos e lógicas reutilizáveis.
- **Stored Procedures** automatizam processos no banco.
- **Triggers** executam ações automáticas diante de eventos específicos.
