# Chapter 7: Comments

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 7: Comments
Examples
Single-line comments

Single line comments are preceded by --, and go until the end of the line:

 SELECT *
 FROM Employees -- this is a comment
 WHERE FName = 'John'



Multi-line comments

Multi-line code comments are wrapped in /* ... */:

 /* This query
    returns all employees */
 SELECT *
 FROM Employees


It is also possible to insert such a comment into the middle of a line:

 SELECT /* all columns: */ *
 FROM Employees


Read Comments online: https://riptutorial.com/sql/topic/1597/comments
