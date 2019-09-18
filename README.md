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
