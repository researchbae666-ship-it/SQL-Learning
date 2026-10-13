# Chapter 2: ALTER TABLE

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 2: ALTER TABLE
Introduction
ALTER command in SQL is used to modify column/constraint in a table


Syntax
   • ALTER TABLE [table_name] ADD [column_name] [datatype]


Examples
Add Column(s)

 ALTER TABLE Employees
 ADD StartingDate date NOT NULL DEFAULT GetDate(),
     DateOfBirth date NULL


The above statement would add columns named StartingDate which cannot be NULL with default
value as current date and DateOfBirth which can be NULL in Employees table.

Drop Column

 ALTER TABLE Employees
 DROP COLUMN salary;


This will not only delete information from that column, but will drop the column salary from table
employees(the column will no more exist).

Drop Constraint

 ALTER TABLE Employees
 DROP CONSTRAINT DefaultSalary


This Drops a constraint called DefaultSalary from the employees table definition.

Note:- Ensure that constraints of the column are dropped before dropping a column.

Add Constraint

 ALTER TABLE Employees
 ADD CONSTRAINT DefaultSalary DEFAULT ((100)) FOR [Salary]


This adds a constraint called DefaultSalary which specifies a default of 100 for the Salary column.



A constraint can be added at the table level.

Types of constraints

   • Primary Key - prevents a duplicate record in the table
   • Foreign Key - points to a primary key from another table
   • Not Null - prevents null values from being entered into a column
   • Unique - uniquely identifies each record in the table
   • Default - specifies a default value
   • Check - limits the ranges of values that can be placed in a column

To learn more about constraints, see the Oracle documentation.

Alter Column

 ALTER TABLE Employees
 ALTER COLUMN StartingDate DATETIME NOT NULL DEFAULT (GETDATE())


This query will alter the column datatype of StartingDate and change it from simple date to datetime
and set default to current date.

Add Primary Key

 ALTER TABLE EMPLOYEES ADD pk_EmployeeID PRIMARY KEY (ID)


This will add a Primary key to the table Employees on the field ID. Including more than one column
name in the parentheses along with ID will create a Composite Primary Key. When adding more
than one column, the column names must be separated by commas.

 ALTER TABLE EMPLOYEES ADD pk_EmployeeID PRIMARY KEY (ID, FName)


Read ALTER TABLE online: https://riptutorial.com/sql/topic/356/alter-table
