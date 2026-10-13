---
lesson_id: C11-L01
chapter: 11
lesson: 1
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C11-L01: Create a New Table

**Chapter:** 11 · **Lesson:** 1 of 4 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Chapter 11: CREATE TABLE
Introduction
The CREATE TABLE statement is used create a new table in the database. A table definition
consists of a list of columns, their types, and any integrity constraints.


Syntax
   • CREATE TABLE tableName( [ColumnName1] [datatype1] [, [ColumnName2] [datatype2] ...]
     )


Parameters

 Parameter      Details

 tableName      The name of the table

                Contains an 'enumeration' of all the columns that the table have. See Create a
 columns
                New Table for more details.


Remarks
Table names must be unique.


Examples
Create a New Table

A basic Employees table, containing an ID, and the employee's first and last name along with their
phone number can be created using

 CREATE TABLE Employees(
     Id int identity(1,1) primary key not null,
     FName varchar(20) not null,
     LName varchar(20) not null,
     PhoneNumber varchar(10) not null
 );


This example is specific to Transact-SQL

CREATE TABLE creates a new table in the database, followed by the table name, Employees


This is then followed by the list of column names and their properties, such as the ID



 Id int identity(1,1) not null



 Value            Meaning

 Id               the column's name.

 int              is the data type.

                  states that column will have auto generated values starting at 1 and
 identity(1,1)
                  incrementing by 1 for each new row.

 primary key      states that all values in this column will have unique values

 not null         states that this column cannot have null values

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
