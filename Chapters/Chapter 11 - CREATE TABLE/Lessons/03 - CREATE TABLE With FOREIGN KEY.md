---
lesson_id: C11-L03
chapter: 11
lesson: 3
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C11-L03: CREATE TABLE With FOREIGN KEY

**Chapter:** 11 · **Lesson:** 3 of 4 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

CREATE TABLE With FOREIGN KEY

Below you could find the table Employees with a reference to the table Cities.

 CREATE TABLE Cities(
     CityID INT IDENTITY(1,1) NOT NULL,
     Name VARCHAR(20) NOT NULL,
     Zip VARCHAR(10) NOT NULL
 );

 CREATE TABLE Employees(
     EmployeeID INT IDENTITY (1,1) NOT NULL,
     FirstName VARCHAR(20) NOT NULL,




       LastName VARCHAR(20) NOT NULL,
       PhoneNumber VARCHAR(10) NOT NULL,
       CityID INT FOREIGN KEY REFERENCES Cities(CityID)
 );


Here could you find a database diagram.




The column CityID of table Employees will reference to the column CityID of table Cities. Below you
could find the syntax to make this.

 CityID INT FOREIGN KEY REFERENCES Cities(CityID)



 Value             Meaning

 CityID            Name of the column

 int               type of the column

 FOREIGN KEY       Makes the foreign key (optional)

 REFERENCES        Makes the reference
 Cities(CityID)    to the table Cities column CityID

Important: You couldn't make a reference to a table that not exists in the database. Be source to
make first the table Cities and second the table Employees. If you do it vise versa, it will throw an
error.

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
