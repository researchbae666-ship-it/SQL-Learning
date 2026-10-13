---
lesson_id: C59-L01
chapter: 59
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C59-L01: Transaction In a TRY/CATCH

## Textbook excerpt

Chapter 59: TRY/CATCH
Remarks
TRY/CATCH is a language construct specific to MS SQL Server's T-SQL.

It allows error handling within T-SQL, similar to that seen in .NET code.


Examples
Transaction In a TRY/CATCH

This will rollback both inserts due to an invalid datetime:

 BEGIN TRANSACTION
 BEGIN TRY
     INSERT INTO dbo.Sale(Price, SaleDate, Quantity)
     VALUES (5.2, GETDATE(), 1)
     INSERT INTO dbo.Sale(Price, SaleDate, Quantity)
     VALUES (5.2, 'not a date', 1)
     COMMIT TRANSACTION
 END TRY
 BEGIN CATCH
     THROW
     ROLLBACK TRANSACTION
 END CATCH


This will commit both inserts:

 BEGIN TRANSACTION
 BEGIN TRY
     INSERT INTO dbo.Sale(Price, SaleDate, Quantity)
     VALUES (5.2, GETDATE(), 1)
     INSERT INTO dbo.Sale(Price, SaleDate, Quantity)
     VALUES (5.2, GETDATE(), 1)
     COMMIT TRANSACTION
 END TRY
 BEGIN CATCH
     THROW
     ROLLBACK TRANSACTION
 END CATCH


Read TRY/CATCH online: https://riptutorial.com/sql/topic/4420/try-catch

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
