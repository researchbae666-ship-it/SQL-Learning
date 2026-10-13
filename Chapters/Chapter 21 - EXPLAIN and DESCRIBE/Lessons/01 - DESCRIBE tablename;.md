---
lesson_id: C21-L01
chapter: 21
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C21-L01: DESCRIBE tablename;

## Textbook excerpt

Chapter 21: EXPLAIN and DESCRIBE
Examples
DESCRIBE tablename;

DESCRIBE and EXPLAIN are synonyms. DESCRIBE on a tablename returns the definition of the columns.


 DESCRIBE tablename;


Exmple Result:

 COLUMN_NAME       COLUMN_TYPE      IS_NULLABLE      COLUMN_KEY     COLUMN_DEFAULT     EXTRA
 id                int(11)          NO               PRI            0
 auto_increment
 test              varchar(255)     YES                             (null)


Here you see the column names, followed by the columns type. It shows if null is allowed in the
column and if the column uses an Index. the default value is also displayed and if the table
contains any special behavior like an auto_increment.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
