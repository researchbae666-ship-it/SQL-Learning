---
lesson_id: C24-L02
chapter: 24
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C24-L02: Foreign Keys explained

## Textbook excerpt

Foreign Keys explained

Foreign Keys constraints ensure data integrity, by enforcing that values in one table must match
values in another table.

An example of where a foreign key is required is: In a university, a course must belong to a
department. Code for the this scenario is:

 CREATE TABLE Department (
     Dept_Code        CHAR (5)     PRIMARY KEY,
     Dept_Name        VARCHAR (20) UNIQUE
 );


Insert values with the following statement:

 INSERT INTO Department VALUES ('CS205', 'Computer Science');


The following table will contain the information of the subjects offered by the Computer science
branch:

 CREATE TABLE Programming_Courses (
     Dept_Code       CHAR(5),
     Prg_Code        CHAR(9) PRIMARY KEY,
     Prg_Name        VARCHAR (50) UNIQUE,
     FOREIGN KEY (Dept_Code) References Department(Dept_Code)
 );





(The data type of the Foreign Key must match the datatype of the referenced key.)

The Foreign Key constraint on the column Dept_Code allows values only if they already exist in the
referenced table, Department. This means that if you try to insert the following values:

 INSERT INTO Programming_Courses Values ('CS300', 'FDB-DB001', 'Database Systems');


the database will raise a Foreign Key violation error, because CS300 does not exist in the Department
table. But when you try a key value that exists:

 INSERT INTO Programming_Courses VALUES ('CS205', 'FDB-DB001', 'Database Systems');
 INSERT INTO Programming_Courses VALUES ('CS205', 'DB2-DB002', 'Database Systems II');


then the database allows these values.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
