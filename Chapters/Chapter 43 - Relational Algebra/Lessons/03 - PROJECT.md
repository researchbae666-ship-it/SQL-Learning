---
lesson_id: C43-L03
chapter: 43
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C43-L03: PROJECT

## Textbook excerpt

PROJECT
The project operator will return distinct field values from a table.
project < table > over < field list >

For example, examine the following expression:
project People over StartYear

This can be written as:



This will result in a table comprising of the distinct values held within the StartYear field of the
People table.




Duplicate values are removed from the resulting table due to the closure property creating a
relational table: all records in a relational table are required to be distinct.

If the field list comprises more than a single field then the resulting table is a distinct version of
these fields.
project People over StartYear, DepartmentID will return:




One record is removed due to the duplication of 2006 StartYear and 1 DepartmentID.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
