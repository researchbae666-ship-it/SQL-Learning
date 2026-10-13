---
lesson_id: C34-L01
chapter: 34
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C34-L01: Insert New Row

## Textbook excerpt

Chapter 34: INSERT
Syntax
   • INSERT INTO table_name (column1,column2,column3,...) VALUES
     (value1,value2,value3,...);
   • INSERT INTO table_name (column1, column2...) SELECT value1, value2... from other_table


Examples
Insert New Row

 INSERT INTO Customers
 VALUES ('Zack', 'Smith', 'zack@example.com', '7049989942', 'EMAIL');


This statement will insert a new row into the Customers table. Note that a value was not specified
for the Id column, as it will be added automatically. However, all other column values must be
specified.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
