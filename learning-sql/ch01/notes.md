# 1. A little background
## Introduction to databases
- A database is nothing more than a set of related information.
- Because of the cumbersome nature of paper databases, some of the first computer applications developed were database systems.

### Nonrelational database systems
- Over the first several decades of computerized database systems, data was stored and represented to users in various ways, for example:
  - Hierarchical database system, where data is represented as one or more tree structures.
  - Network database system, that exposes sets of records and sets of links that define relationships between different records.
  - Both database systems are alive and well today, although generally in the mainframe world.

### The relational model
- Data be represented as sets of tables, rather than using pointers to navigate between related entities, redundant data is used to link records in different tables.
- Each table includes information that uniquely indentifies a row in that table (known as the **primary key**), along with additional information needed to describe the entity completely.
- A primary key consisting of two or more columns is known as **compound key**.
- Some of the tables also include information used to navigate to another table; this is wher ethe "redundant data" mentioned earlier comes in.
  - These columns are known as **foreign keys**.
- The process of refining a database design to ensure that each independent piece of information is in only one place (except for foreign keys) is known as **normalization**.

### Some terminology
|Term|Definition|
|:---|:---|
|Entity|Something of interest to the database user community. Examples include customers, parts, geographic locations, etc.|
|Column|An individual piece of data stored in a table.|
|Row|A set of columns that together completely describe an entity or some action on an entity. Also called a record.|
|Table|A set of rows, held either in memory (nonpersistent) or on permanent storage (persisten).|
|Result set|Another name for a nonpersistent table, generally the result of an SQL query.|
|Primary key|One or more columns that can be used as a unique identifier for each row in a table.|
|Foreign key|One or more columns that can be used together to identify a single row in another table.|

## What is SQL?
- While SQL began as a language used to manipulate data in relational databases, it has evolved to be a language for manipulating data across various database technologies.

### SQL statement classes
- The SQL language is divided into several distinct parts:
  - Schema statement, which are used to define the data structures stored in the database.
  - SQL data statements, which are used to manipulate the data structures previously defined using SQL schema statements.
  - SQL transactional statements, which are used to begin, end, and roll back transactions.
- All database elements created via SQL schema statements are stored in a special set of tables called the **data dictionary**.
  - This "data about the database" is known collectively as **metada**.

### SQL: a nonprocedural language
- With SQL, statements define the necessary inputs and outputs, but the manner in which a statement is executed is left to a component of your database engine knwon as the **optimizer**.
  - Its job is to look at your SQL statements and, taking into account how your tables are configured and what indexes are available, decide the most efficient execution path.

### SQL Examples
- Almost every query that you encounter will include at least `select`, `from`, and `where`, although there are several more that can be used for more specialized purposes.
  - `SELECT` one or more things
  - `FROM` one or more places
  - `WHERE` one or more conditions apply
- Example:

```sql
SELECT cust_id, fname
FROM individual
WHERE lname = 'Smith';
```

  - This query searches the `individual` table for all rows whose `lname` column matches the string `Smith` and returns the `cust_id` and `fname` columsn from those rows.

- Example of how you would insert a new row into the `product` table:

```sql
INSERT INTO product(product_cd, name)
VALUES('CD', 'Certificate of Depysit');
```

- `Update` statement:

```sql
UPDATE product
SET name = 'Certificate of Deposit'
WHERE product_cd = 'CD';
```

## What is MySQL?

## SQL unplugged
- While relational databases are still heavily used and will continue to be for some time, new database technologies have emerged to meet the needs of companies like Amazon and Google.
  - These technologies include Hadoop, Spark, NoSQL, and NewSQL.
  - They all shre something in common with relational databases: SQL.
- There is a need to unplug SQL from a particular database server and provide a service that can span multiple databases.
  - A new generation of tool shave been to meet this type of challenge, and one of the most promising is Apache Drill, which is an open source query engine that allows users to write queries that can access data stored in most any database or filesystem. (Chapter 18)

## What's in store
