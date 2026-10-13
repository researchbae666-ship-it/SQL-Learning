---
lesson_id: C29-L02
chapter: 29
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C29-L02: Filter GROUP BY results using a HAVING clause

## Textbook excerpt

Filter GROUP BY results using a HAVING clause

A HAVING clause filters the results of a GROUP BY expression. Note: The following examples are
using the Library example database.

Examples:

Return all authors that wrote more than one book (live example).

 SELECT
   a.Id,
   a.Name,
   COUNT(*) BooksWritten
 FROM BooksAuthors ba
   INNER JOIN Authors a ON a.id = ba.authorid
 GROUP BY
   a.Id,
   a.Name
 HAVING COUNT(*) > 1     -- equals to HAVING BooksWritten > 1
 ;


Return all books that have more than three authors (live example).

 SELECT
   b.Id,
   b.Title,
   COUNT(*) NumberOfAuthors
 FROM BooksAuthors ba
   INNER JOIN Books b ON b.id = ba.bookid
 GROUP BY
   b.Id,
   b.Title
 HAVING COUNT(*) > 3    -- equals to HAVING NumberOfAuthors > 3
 ;

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
