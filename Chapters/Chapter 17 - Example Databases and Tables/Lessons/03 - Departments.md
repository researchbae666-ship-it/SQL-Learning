---
lesson_id: C17-L03
chapter: 17
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C17-L03: Departments

## Textbook excerpt

Departments

 Id     Name

 1      HR

 2      Sales

 3      Tech

SQL statements to create the table:

 CREATE TABLE Departments (
     Id INT NOT NULL AUTO_INCREMENT,
     Name VARCHAR(25) NOT NULL,
     PRIMARY KEY(Id)
 );

 INSERT INTO Departments
     ([Id], [Name])
 VALUES
     (1, 'HR'),
     (2, 'Sales'),
     (3, 'Tech')
 ;

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
