---
lesson_id: C32-L03
chapter: 32
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C32-L03: Inserting with a Unique Index

## Textbook excerpt

Inserting with a Unique Index

 UPDATE Customers SET Email = "richard0123@example.com" WHERE id = 1;


This will fail if an unique index is set on the Email column of Customers. However, alternate
behavior can be defined for this case:

 UPDATE Customers SET Email = "richard0123@example.com" WHERE id = 1 ON DUPLICATE KEY;

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
