---
lesson_id: C03-L01
chapter: 3
lesson: 1
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C03-L01: AND OR Example

**Chapter:** 3 · **Lesson:** 1 of 1 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Chapter 3: AND & OR Operators
Syntax
   1. SELECT * FROM table WHERE (condition1) AND (condition2);

   2. SELECT * FROM table WHERE (condition1) OR (condition2);


Examples
AND OR Example

Have a table

 Name     Age     City

 Bob      10      Paris

 Mat      20      Berlin

 Mary     24      Prague

 select Name from table where Age>10 AND City='Prague'


Gives

 Name

 Mary


 select Name from table where Age=10 OR City='Prague'


Gives

 Name

 Bob

 Mary

Read AND & OR Operators online: https://riptutorial.com/sql/topic/1386/and---or-operators

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
