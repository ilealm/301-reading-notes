# Read 08, SQL


* Stands for Structured Query Language.
* Allws users query, manipulate, and transform data from a relational database. 
* SQL databases provide safe and scalable storage for websites and mobile applications.
* Popular SQL databases including: SQLite, MySQL, Postgres, Oracle and Microsoft SQL Server. 


### Relational Database
* Represents a collection of related (two-dimensional) tables, with a fixed number of named columns  and any number of rows of data.
* The columns represent the attributes or properties of the table.

### Retrieve data from a SQL database

* To retrieve data from a SQL database, we need to write SELECT statements, which are often colloquially refered to as queries.
* A query is a statement which declares:
  1. What data we are looking for, 
  1. Where to find it in the database, 
  1. Optionally, how to transform it before it is returned. 

### _Select query for a specific columns_

>`SELECT column, another_column, …`
>`FROM mytable;`

_The result of this query will be a two-dimensional set of rows and columns, effectively a copy of the table, but only with the columns that we requested._

### _Select query for a All columns on a table_

> SELECT * 
> FROM mytable;

### Queries with constraints, AKA Where clause
* In order to filter certain results from being returned, we can to use a WHERE clause in the query. 
* The clause is applied to each row of data by checking specific column values to determine whether it should be included in the results or not.
* Clauses can be constructed by joining numerous AND or OR logical keywords:
  - =, !=, < <=, >, >=+
  - BETWEEN … AND …
  - NOT BETWEEN … AND
  - IN (…)
  - NOT IN (…)
  - = _(Case sensitive exact string comparison)_
  - != or <>
  - LIKE _(Case insensitive exact string comparison)_
  - NOT LIKE
  - % _(Used anywhere in a string to match a sequence of zero or more characters (only with LIKE or NOT LIKE))_
  - _ _(Used anywhere in a string to match a single character (only with LIKE or NOT LIKE))_

> `Select query with constraints`
> `SELECT column, another_column, …`
> `FROM mytable`
> `WHERE condition`
> `    AND/OR another_condition`
> `    AND/OR …;`

### Filtering and sorting Query results

* SQL provides a convenient way to discard rows that have a duplicate column value by using the DISTINCT keyword.

#### Select query with unique results
> `Select query with unique results`
> `SELECT DISTINCT column, another_column, …`
> `FROM mytable`
> `WHERE condition(s);`

* SQL provides a way to sort your results by a given column in ascending or descending order using the ORDER BY clause.
  - The LIMIT will reduce the number of rows to return, and the optional OFFSET will specify where to begin counting the number rows from.

#### Select query with ordered results
> `SELECT column, another_column, …`
> `FROM mytable`
> `WHERE condition(s)`
> `ORDER BY column ASC/DESC;`
> `LIMIT num_limit OFFSET num_offset;`

