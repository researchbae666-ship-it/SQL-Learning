---
lesson_id: C42-L01
chapter: 42
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C42-L01: Creating a Primary Key

## Textbook excerpt

Chapter 42: Primary Keys
Syntax
   • MySQL: CREATE TABLE Employees ( Id int NOT NULL, PRIMARY KEY (Id), ... );

   • Others: CREATE TABLE Employees ( Id int NOT NULL PRIMARY KEY, ... );


Examples
Creating a Primary Key

 CREATE TABLE Employees (
     Id int NOT NULL,
     PRIMARY KEY (Id),
     ...
 );


This will create the Employees table with 'Id' as its primary key. The primary key can be used to
uniquely identify the rows of a table. Only one primary key is allowed per table.

A key can also be composed by one or more fields, so called composite key, with the following
syntax:

 CREATE TABLE EMPLOYEE (
     e1_id INT,
     e2_id INT,
     PRIMARY KEY (e1_id, e2_id)
 )

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
