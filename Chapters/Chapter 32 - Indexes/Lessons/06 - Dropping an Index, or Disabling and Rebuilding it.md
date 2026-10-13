---
lesson_id: C32-L06
chapter: 32
lesson: 6
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C32-L06: Dropping an Index, or Disabling and Rebuilding it

## Textbook excerpt

Dropping an Index, or Disabling and Rebuilding it

 DROP INDEX ix_cars_employee_id ON Cars;


We can use command DROP to delete our index. In this example we will DROP the index called
ix_cars_employee_id on the table Cars.

This deletes the index entirely, and if the index is clustered, will remove any clustering. It cannot
be rebuilt without recreating the index, which can be slow and computationally expensive. As an
alternative, the index can be disabled:

 ALTER INDEX ix_cars_employee_id ON Cars DISABLE;




This allows the table to retain the structure, along with the metadata about the index.

Critically, this retains the index statistics, so that it is possible to easily evaluate the change. If
warranted, the index can then later be rebuilt, instead of being recreated completely;

 ALTER INDEX ix_cars_employee_id ON Cars REBUILD;

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
