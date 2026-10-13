# Chapter 42: Primary Keys

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

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
