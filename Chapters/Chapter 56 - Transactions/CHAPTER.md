# Chapter 56: Transactions

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

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



Rollback Transaction

When something fails in your transaction code and you want to undo it, you can rollback your
transaction:

 BEGIN TRY
     BEGIN TRANSACTION
         INSERT INTO Users(ID, Name, Age)
         VALUES(1, 'Bob', 24)

         DELETE FROM Users WHERE Name = 'Todd'
    COMMIT TRANSACTION
 END TRY
 BEGIN CATCH
    ROLLBACK TRANSACTION
 END CATCH


Read Transactions online: https://riptutorial.com/sql/topic/2424/transactions
