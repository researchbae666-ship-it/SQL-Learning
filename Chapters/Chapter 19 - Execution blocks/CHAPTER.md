# Chapter 19: Execution blocks

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 19: Execution blocks
Examples
Using BEGIN ... END

 BEGIN
   UPDATE Employees SET PhoneNumber = '5551234567' WHERE Id = 1;
   UPDATE Employees SET Salary = 650 WHERE Id = 3;
 END


Read Execution blocks online: https://riptutorial.com/sql/topic/1632/execution-blocks
