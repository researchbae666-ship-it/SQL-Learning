---
lesson_id: C32-L09
chapter: 32
lesson: 9
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C32-L09: Clustered index

## Textbook excerpt

Clustered index

When using clustered index, the rows of the table are sorted by the column to which the clustered
index is applied. Therefore, there can be only one clustered index on the table because you can't
order the table by two different columns.

Generally, it is best to use clustered index when performing reads on big data tables. The
donwside of clustered index is when writing to table and data need to be reorganized (resorted).

An example of creating a clustered index on a table Employees on column Employee_Surname:

 CREATE CLUSTERED INDEX ix_employees_name ON Employees(Employee_Surname);

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
