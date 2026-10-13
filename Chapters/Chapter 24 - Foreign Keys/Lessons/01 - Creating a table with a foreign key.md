---
lesson_id: C24-L01
chapter: 24
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C24-L01: Creating a table with a foreign key

## Textbook excerpt

Chapter 24: Foreign Keys
Examples
Creating a table with a foreign key

In this example we have an existing table, SuperHeros.

This table contains a primary key ID.

We will add a new table in order to store the powers of each super hero:

 CREATE TABLE HeroPowers
 (
     ID int NOT NULL PRIMARY KEY,
     Name nvarchar(MAX) NOT NULL,
     HeroId int REFERENCES SuperHeros(ID)
 )


The column HeroId is a foreign key to the table SuperHeros.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
