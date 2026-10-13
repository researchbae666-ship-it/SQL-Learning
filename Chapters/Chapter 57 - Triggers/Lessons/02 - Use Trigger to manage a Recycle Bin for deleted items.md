---
lesson_id: C57-L02
chapter: 57
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C57-L02: Use Trigger to manage a "Recycle Bin" for deleted items

## Textbook excerpt

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

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
