---
lesson_id: C32-L10
chapter: 32
lesson: 10
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C32-L10: Non clustered index

## Textbook excerpt

Non clustered index

Nonclustered indexes are stored separately from the table. Each index in this structure contains a



pointer to the row in the table which it represents.

This pointers are called a row locators. The structure of the row locator depends on whether the
data pages are stored in a heap or a clustered table. For a heap, a row locator is a pointer to the
row. For a clustered table, the row locator is the clustered index key.

An example of creating a non clustered index on table Employees and column
Employee_Surname:

 CREATE NONCLUSTERED INDEX ix_employees_name ON Employees(Employee_Surname);


There can be multiple nonclustered indexes on the table. The read operations are generally slower
with non clustered indexes than with clustered indexes as you have to go first to index and than to
the table. There are no restrictions in write operations however.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
