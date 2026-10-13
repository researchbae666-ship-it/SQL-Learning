# Chapter 57: Triggers

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

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



Use Trigger to manage a "Recycle Bin" for deleted items

 CREATE TRIGGER BooksDeleteTrigger
      ON MyBooksDB.Books
      AFTER DELETE
 AS
    INSERT INTO BooksRecycleBin
      SELECT *
      FROM deleted;
 GO


Read Triggers online: https://riptutorial.com/sql/topic/1432/triggers
