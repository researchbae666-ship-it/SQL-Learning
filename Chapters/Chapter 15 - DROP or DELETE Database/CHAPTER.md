# Chapter 15: DROP or DELETE Database

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

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
