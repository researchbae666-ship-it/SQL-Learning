---
lesson_id: C39-L02
chapter: 39
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C39-L02: Nullable columns in tables

## Textbook excerpt

Nullable columns in tables

When creating tables it is possible to declare a column as nullable or non-nullable.

 CREATE TABLE MyTable
 (
     MyCol1 INT NOT NULL, -- non-nullable
     MyCol2 INT NULL      -- nullable
 ) ;


By default every column (except those in primary key constraint) is nullable unless we explicitly set
NOT NULL constraint.


Attempting to assign NULL to a non-nullable column will result in an error.

 INSERT INTO MyTable (MyCol1, MyCol2) VALUES (1, NULL) ;        -- works fine

 INSERT INTO MyTable (MyCol1, MyCol2) VALUES (NULL, 2) ;




          -- cannot insert
          -- the value NULL into column 'MyCol1', table 'MyTable';
          -- column does not allow nulls. INSERT fails.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
