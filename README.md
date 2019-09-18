### SQL Summary Information

## Databases

A DATABASE is a structured set of data, usually held in a computer, that is accessible in various ways.

We will look largely at Relational Databases. They contain connected data that are separated into numerous tables, linked together by use of Keys.

## Types of relationship
- One-to-one: Each row in table A is linked to no more than one row in table B. This is an attribute of the relationship, not the tables. A student may have one row in the Contact_info Table.
- One-to-many: Each row in the table can be relayed on to many rows in the relating table. This allows frequently used information to be saved only once in a table and referenced many times in the other tables.
- Many-to-many: One or more rows in a table can be related to 0, 1 or many rows in another table. A 3rd table called a mapping or link table is required in order to implement such a relationship. For example, customers can purchase many products.
