---
lesson_id: C15-L01
chapter: 15
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C15-L01: DROP Database

## Textbook excerpt

Chapter 15: DROP or DELETE Database
Syntax
   • MSSQL Syntax:
   • DROP DATABASE [ IF EXISTS ] { database_name | database_snapshot_name } [ ,...n ] [;]
   • MySQL Syntax:
   • DROP {DATABASE | SCHEMA} [IF EXISTS] db_name


Remarks
DROP DATABASE is used for dropping a database from SQL. Be sure to create a backup of your
database before dropping it to prevent accidental loss of information.


Examples
DROP Database

Dropping the database is a simple one-liner statement. Drop database will delete the database,
hence always ensure to have a backup of the database if required.

Below is the command to drop Employees Database

 DROP DATABASE [dbo].[Employees]


Read DROP or DELETE Database online: https://riptutorial.com/sql/topic/3974/drop-or-delete-
database

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
