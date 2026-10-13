---
lesson_id: C17-L09
chapter: 17
lesson: 9
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C17-L09: Books

## Textbook excerpt

Books
(view table)

 Id   Title

 1    The Catcher in the Rye

 2    Nine Stories

 3    Franny and Zooey

 4    The Great Gatsby

 5    Tender id the Night

 6    Pride and Prejudice

 7    Professional ASP.NET 4.5 in C# and VB

SQL to create the table:

 CREATE TABLE Books (
     Id INT NOT NULL AUTO_INCREMENT,
     Title VARCHAR(50) NOT NULL,
     PRIMARY KEY(Id)
 );

 INSERT INTO Books
     (Id, Title)
 VALUES
     (1, 'The Catcher in the Rye'),
     (2, 'Nine Stories'),
     (3, 'Franny and Zooey'),
     (4, 'The Great Gatsby'),
     (5, 'Tender id the Night'),
     (6, 'Pride and Prejudice'),
     (7, 'Professional ASP.NET 4.5 in C# and VB')
 ;

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
