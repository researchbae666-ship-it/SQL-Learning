---
lesson_id: C34-L03
chapter: 34
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C34-L03: INSERT data from another table using SELECT

## Textbook excerpt

INSERT data from another table using SELECT

 INSERT INTO Customers (FName, LName, PhoneNumber)
 SELECT FName, LName, PhoneNumber FROM Employees


This example will insert all Employees into the Customers table. Since the two tables have
different fields and you don't want to move all the fields over, you need to set which fields to insert
into and which fields to select. The correlating field names don't need to be called the same thing,
but then need to be the same data type. This example is assuming that the Id field has an Identity
Specification set and will auto increment.

If you have two tables that have exactly the same field names and just want to move all the
records over you can use:

 INSERT INTO Table1
 SELECT * FROM Table2

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
