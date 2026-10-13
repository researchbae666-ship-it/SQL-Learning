---
lesson_id: C56-L01
chapter: 56
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C56-L01: Simple Transaction

## Textbook excerpt

Chapter 56: Transactions
Remarks
A transaction is a logical unit of work containing one or more steps, each of which must complete
successfully in order for the transaction to commit to the database. If there are errors, then all of
the data modifications are erased and the database is rolled back to its initial state at the start of
the transaction.


Examples
Simple Transaction

 BEGIN TRANSACTION
     INSERT INTO DeletedEmployees(EmployeeID, DateDeleted, User)
         (SELECT 123, GetDate(), CURRENT_USER);
     DELETE FROM Employees WHERE EmployeeID = 123;
 COMMIT TRANSACTION

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
