# Chapter 51: Stored Procedures

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 51: Stored Procedures
Remarks
Stored Procedures are SQL statements stored in the database that can be executed or called in
queries. Using a stored procedure allows encapsulation of complicated or frequently used logic,
and improves query performance by utilizing cached query plans. They can return any value a
standard query can return.

Other benefits over dynamic SQL expressions are listed on Wikipeida.


Examples
Create and call a stored procedure

Stored procedures can be created through a database management GUI (SQL Server example),
or through a SQL statement as follows:

 -- Define a name and parameters
 CREATE PROCEDURE Northwind.getEmployee
     @LastName nvarchar(50),
     @FirstName nvarchar(50)
 AS

 -- Define the query to be run
 SELECT FirstName, LastName, Department
 FROM Northwind.vEmployeeDepartment
 WHERE FirstName = @FirstName AND LastName = @LastName
 AND EndDate IS NULL;


Calling the procedure:

 EXECUTE Northwind.getEmployee N'Ackerman', N'Pilar';

 -- Or
 EXEC Northwind.getEmployee @LastName = N'Ackerman', @FirstName = N'Pilar';
 GO

 -- Or
 EXECUTE Northwind.getEmployee @FirstName = N'Pilar', @LastName = N'Ackerman';
 GO


Read Stored Procedures online: https://riptutorial.com/sql/topic/1701/stored-procedures
