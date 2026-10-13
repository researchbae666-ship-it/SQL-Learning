---
lesson_id: C06-L01
chapter: 6
lesson: 1
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C06-L01: Formatting and Spelling of Keywords and Names

**Chapter:** 6 · **Lesson:** 1 of 4 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Chapter 6: Clean Code in SQL
Introduction
How to write good, readable SQL queries, and example of good practices.


Examples
Formatting and Spelling of Keywords and Names


Table/Column Names
Two common ways of formatting table/column names are CamelCase and snake_case:

 SELECT FirstName, LastName
 FROM Employees
 WHERE Salary > 500;


 SELECT first_name, last_name
 FROM employees
 WHERE salary > 500;


Names should describe what is stored in their object. This implies that column names usually
should be singular. Whether table names should use singular or plural is a heavily discussed
question, but in practice, it is more common to use plural table names.

Adding prefixes or suffixes like tbl or col reduces readability, so avoid them. However, they are
sometimes used to avoid conflicts with SQL keywords, and often used with triggers and indexes
(whose names are usually not mentioned in queries).


Keywords
SQL keywords are not case sensitive. However, it is common practice to write them in upper case.

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
