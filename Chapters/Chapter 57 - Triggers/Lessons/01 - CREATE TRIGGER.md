---
lesson_id: C57-L01
chapter: 57
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C57-L01: CREATE TRIGGER

## Textbook excerpt

Chapter 57: Triggers
Examples
CREATE TRIGGER

This example creates a trigger that inserts a record to a second table (MyAudit) after a record is
inserted into the table the trigger is defined on (MyTable). Here the "inserted" table is a special
table used by Microsoft SQL Server to store affected rows during INSERT and UPDATE
statements; there is also a special "deleted" table that performs the same function for DELETE
statements.

 CREATE TRIGGER MyTrigger
     ON MyTable
     AFTER INSERT

 AS

 BEGIN
     -- insert audit record to MyAudit table
     INSERT INTO MyAudit(MyTableId, User)
     (SELECT MyTableId, CURRENT_USER FROM inserted)
 END

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
