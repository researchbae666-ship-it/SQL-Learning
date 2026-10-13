---
lesson_id: C56-L02
chapter: 56
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C56-L02: Rollback Transaction

## Textbook excerpt

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

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
