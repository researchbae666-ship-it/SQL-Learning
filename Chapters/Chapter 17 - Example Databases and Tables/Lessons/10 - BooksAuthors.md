---
lesson_id: C17-L10
chapter: 17
lesson: 10
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C17-L10: BooksAuthors

## Textbook excerpt

BooksAuthors
(view table)

 BookId     AuthorId

 1          1

 2          1

 3          1

 4          2

 5          2

 6          3

 7          4

 7          5

 7          6

 7          7

 7          8

SQL to create the table:

 CREATE TABLE BooksAuthors (
     AuthorId INT NOT NULL,
     BookId INT NOT NULL,
     FOREIGN KEY (AuthorId) REFERENCES Authors(Id),
     FOREIGN KEY (BookId) REFERENCES Books(Id)
 );

 INSERT INTO BooksAuthors
     (BookId, AuthorId)
 VALUES
     (1, 1),
     (2, 1),
     (3, 1),
     (4, 2),
     (5, 2),
     (6, 3),
     (7, 4),
     (7, 5),
     (7, 6),
     (7, 7),
     (7, 8)
 ;





Examples
View all authors (view live example):

 SELECT * FROM Authors;


View all book titles (view live example):

 SELECT * FROM Books;


View all books and their authors (view live example):

 SELECT
   ba.AuthorId,
   a.Name AuthorName,
   ba.BookId,
   b.Title BookTitle
 FROM BooksAuthors ba
   INNER JOIN Authors a ON a.id = ba.authorid
   INNER JOIN Books b ON b.id = ba.bookid
 ;

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
