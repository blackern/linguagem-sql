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
