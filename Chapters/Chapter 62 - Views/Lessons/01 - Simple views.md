---
lesson_id: C62-L01
chapter: 62
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C62-L01: Simple views

## Textbook excerpt

Chapter 62: Views
Examples
Simple views

A view can filter some rows from the base table or project only some columns from it:

 CREATE VIEW new_employees_details AS
 SELECT E.id, Fname, Salary, Hire_date
 FROM Employees E
 WHERE hire_date > date '2015-01-01';


If you select form the view:

 select * from new_employees_details



 Id   FName          Salary       Hire_date

 4    Johnathon      500          24-07-2016

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
