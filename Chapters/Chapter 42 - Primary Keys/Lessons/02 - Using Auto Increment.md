---
lesson_id: C42-L02
chapter: 42
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C42-L02: Using Auto Increment

## Textbook excerpt

Using Auto Increment

Many databases allow to make the primary key value automatically increment when a new key is
added. This ensures that every key is different.

MySQL

 CREATE TABLE Employees (
     Id int NOT NULL AUTO_INCREMENT,
     PRIMARY KEY (Id)
 );


PostgreSQL

 CREATE TABLE Employees (
     Id SERIAL PRIMARY KEY
 );





SQL Server

 CREATE TABLE Employees (
     Id int NOT NULL IDENTITY,
     PRIMARY KEY (Id)
 );


SQLite

 CREATE TABLE Employees (
     Id INTEGER PRIMARY KEY
 );


Read Primary Keys online: https://riptutorial.com/sql/topic/505/primary-keys

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
