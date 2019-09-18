### :japanese_goblin: SQL Summary Information :running:

## Databases

A DATABASE is a structured set of data, usually held in a computer, that is accessible in various ways.

We will look largely at Relational Databases. They contain connected data that are separated into numerous tables, linked together by use of Keys.

## Types of relationship
- One-to-one: Each row in table A is linked to no more than one row in table B. This is an attribute of the relationship, not the tables. A student may have one row in the Contact_info Table.
- One-to-many: Each row in the table can be relayed on to many rows in the relating table. This allows frequently used information to be saved only once in a table and referenced many times in the other tables.
- Many-to-many: One or more rows in a table can be related to 0, 1 or many rows in another table. A 3rd table called a mapping or link table is required in order to implement such a relationship. For example, customers can purchase many products.

## Primary Key
- A Primary Key is a unique Key that identifies each reacord in a table.
- Tables should have a PK (Primary Key)
- Each table can have more than one column that is part of its primary key (called a composite key)
- Must be unique
- Must always have an entry, not blank or null
- Must never changed, it made at the inception of the table
- Each table must have a maximum of one primary key
:raised_hands: :v: 
