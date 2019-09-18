# :japanese_goblin: SQL Summary Information :running:

## Databases

A DATABASE is a structured set of data, usually held in a computer, that is accessible in various ways.

We will look largely at Relational Databases. They contain connected data that are separated into numerous tables, linked together by use of Keys.

### Types of relationship :couple: :two_men_holding_hands: :two_women_holding_hands:
- One-to-one: Each row in table A is linked to no more than one row in table B. This is an attribute of the relationship, not the tables. A student may have one row in the Contact_info Table.
- One-to-many: Each row in the table can be relayed on to many rows in the relating table. This allows frequently used information to be saved only once in a table and referenced many times in the other tables.
- Many-to-many: One or more rows in a table can be related to 0, 1 or many rows in another table. A 3rd table called a mapping or link table is required in order to implement such a relationship. For example, customers can purchase many products.

### Primary Key
- A Primary Key is a unique Key that identifies each reacord in a table.
- Tables should have a PK (Primary Key)
- Each table can have more than one column that is part of its primary key (called a composite key)
- Must be unique
- Must always have an entry, not blank or null
- Must never changed, it made at the inception of the table
- Each table must have a maximum of one primary key :point_up:

### Foreign Key
- Natural relationships exist between tables in most databases. Foreign keys used to create solid relationships.
- Foreign keys ensure that the row of information in table A corresponds to the correct row of information in table B
- The constraint is used to prevent actions that would destroy links between tables.
- It prevents invalid data from being inserted into the foreign key column, because it must be one of the values contained in the table it points to.
- There is no uniqueness constraint for foreign keys
- A table can have any number of foreign keys
- A row cannot be deleted from a reference table if it is in use via a foreign key

### Examples of Database Tools
- Microsoft Access
- SQL Server Editions
- PostgreSQL
- SQLite
- MySQL
- Redis - "not only SQL"
- MongoDB - "not only SQL"
- Oracle

### Languages for dealing with data in SQL
- DML: Data Manipulation Language - SELECT, INSERT, UPDATE, DELETE
- DDL: Data Definition Language - CREATE, ALTER, DROP, TRUNCATE
- DCL: Data Control Language - GRANT, REVOKE
- TCL: Transaction Control Language - COMMIT, ROLLBACK, SAVEPOINT

## SQL COMMANDS

### Creating & Using a database
```SQLite
CREATE DATABASE DB_name;

USE DB_name;
```

### Different Types of Data
+ CHAR(n): Set length, n, of data and it always has to be exactly that length.
+ VARCHAR(n): Set length, n, of data and entries can be any length up to that maximum length.
+ INT: Integer value only
+ DECIMAL(n,m)/NUMERIC(n,m): Numbers with a decimal point, n total digits, m digits after decimal point.
+ BINARY - string of 0 & 1's (up to 16 bits)
+ FLOAT - large mathematical number e.g. pi
+ BIT - 0 or 1, boolean

### Creating a Table in your Database
```SQLite
USE DB_name;
CREATE TABLE table_name
(
Column_1 DATA_TYPE
Column_2 DATA_TYPE
Column_3 DATA_TYPE
...
  );
```
### Altering a table - adding a column

```SQLite
USE DB_name
ALTER TABLE table_name ADD Column_name DATA_TYPE;
```

### Modifying a column's data type in a table

```SQLite
USE DB_name
ALTER TABLE table_name
ALTER COLUMN column_name DATA_TYPE;
```

### Change Data in a table
```SQLite
UPDATE table_name
SET column_name_for_change = new_data_input
WHERE column_name_for_basis_of_data_change = condition_on_which_row_to_change; %this condition should define the data point that needs to be changed. It will change all rows with entries that meet the condition, but only change the entry of that row in the column defined in "SET".%
```

### Delete all data in a table
```SQLite
DELETE FROM table_name;
```

### Delete data from a row
```SQLite
DELETE FROM table_name
WHERE column_name_for_basis_of_data_delete = condition_on_which_row_to_delete; %this condition should define the data point that needs to be deleted. This will delete the WHOLE ROWS that fit the condition prescribed on columns.
```

### Using NULL and NOT NULL

You can add the phrase "NOT NULL" to the end of column names when setting up a table to make the column not empty by default.

### Setting up a primary key when setting up a table

Use the phrase "IDENTITY PRIMARY KEY" when setting up a table to select the primary key for that table. If you do not do this, one will be assigned automatically. If you do not do this you will not be able to change it after the table is made.

### Database Considerations
+ Data Security
+ Data Recovery
+ Data Integrity
+ Normal Form

### Normal Form

A database is in its *First Normal Form* when:
- Everything is as small as it can be
- There are no repeating groups

A database is in its *Second Normal Form* when:
- It is in _First Normal Form_
- All non-key attributes are fully functionally dependent on the Primary Key

A database in it its *Third Normal Form* when:
- It is in _Second Normal Form_
- There is no transitive functional dependency, i.e. when a non-key is functionally dependent on another non-key column, which is functionally dependent on the primary key.

### Examples of SQL keywords for syntax
- SELECT
- DISTINCT
- FROM
- WHERE
- GROUP BY
- HAVING
- ORDER BY
- LIKE

### Wildcards
- Using % can substitute for zero or more unknown characters
- _ is used for substituting for a single unknown character
- [character_list] can be used to bring back anything starting with those letters
- [^character_list] can bring back anything that does not start with those letters
All of these are best used with the LIKE keyword when defining a condition using WHERE.

### String Functions
- SUBSTRING(expression, start, length): makes a substring on an existing string, defining where to begin to cut on the existing string and how long to continue for.
- CHARINDEX(letter, column): finds, for example, a letter in a column.
- LEFT/RIGHT(column, n): takes the left/right n characters of a string in a column.
- LTRIM/RTRIM: Used to remove spaces at the beginning or the end of a String.
- LEN(string): finds the length of a given String.
- REPLACE(column, string_to_replace, replace_with_string): Replace strings with other strings in a column.
- UPPER/LOWER: convert a string to lower or upper case.

### DATE Functions
- GETDATE: returns current date
- SYSDATETIME: returns the date and time of the computer being used
- DATEADD(d/m/Y, amount_to_add, given_date): adds a certain number of days/months/years to a given date
- DATEDIFF(d/m/Y, date_earliest, date_latest): finds the difference between two dates in days/months/years
- YEAR(date): gets a year from a date
- MONTH(date): gets a month from a date
- DAY(date): gets a day from a date
- FORMAT(date, 'dd/MM/YYYY'): changes given date to a chosen format

### Using Case in SQL

```SQLite
SELECT CASE
WHEN condition
THEN 'output'
ELSE 'alternative output'
END AS 'column name for condition imposed'
FROM table;
```

### Aggregate Functions
- SUM: grand total of all columns for rows selected
- AVG: average of all the columns rows selected
- MIN/MAX: minimum/maximum in a column for rows selected
- COUNT: for the total number of non-empty entries in rows selected.

These must use a **GROUP BY** clause.

### Joins

```SQLite
SELECT column, AGGREGATE FUNCTION
FROM table_1
JOIN table_2 ON table_1.SAME_COLUMN=table_2.SAME_COLUMN %these two tables need to share the same column data e.g. a primary key would be good%
WHERE condition
GROUP BY column;
```
### Sub-Query
Is a nested query inside another SELECT statement, which allows you to take the results of one query and use it in another.
```SQLite
SELECT column_1 FROM table_1
WHERE column_x NOT IN (SELECT column_x FROM table_2)
