# Chapter 59: TRY/CATCH

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

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
