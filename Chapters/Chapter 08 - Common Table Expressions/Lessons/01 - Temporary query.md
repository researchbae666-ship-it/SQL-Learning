---
lesson_id: C08-L01
chapter: 8
lesson: 1
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C08-L01: Temporary query

**Chapter:** 8 · **Lesson:** 1 of 6 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Chapter 8: Common Table Expressions
Syntax
   • WITH QueryName [(ColumnName, ...)] AS (
       SELECT ...
     )
     SELECT ... FROM QueryName ...;

   • WITH RECURSIVE QueryName [(ColumnName, ...)] AS (
       SELECT ...
       UNION [ALL]
       SELECT ... FROM QueryName ...
     )
     SELECT ... FROM QueryName ...;


Remarks
Official documentation: WITH clause

A Common Table Expression is a temporary result set, and it can be result of complex sub query.
It is defined by using WITH clause. CTE improves readability and it is created in memory rather
than TempDB database where Temp Table and Table variable is created.

Key concepts of Common Table Expressions:

   • Can be used to break up complex queries, especially complex joins and sub-queries.
   • Is a way of encapsulating a query definition.
   • Persist only until the next query is run.
   • Correct use can lead to improvements in both code quality/maintainability and speed.
   • Can be used to reference the resulting table multiple times in the same statement (eliminate
     duplication in SQL).
   • Can be a substitute for a view when the general use of a view is not required; that is, you do
     not have to store the definition in metadata.
   • Will be run when called, not when defined. If the CTE is used multiple times in a query it will
     be run multiple times (possibly with different results).


Examples
Temporary query

These behave in the same manner as nested subqueries but with a different syntax.

 WITH ReadyCars AS (
   SELECT *




     FROM Cars
     WHERE Status = 'READY'
 )
 SELECT ID, Model, TotalCost
 FROM ReadyCars
 ORDER BY TotalCost;



 ID    Model         TotalCost

 1     Ford F-150    200

 2     Ford F-150    230

Equivalent subquery syntax

 SELECT ID, Model, TotalCost
 FROM (
   SELECT *
   FROM Cars
   WHERE Status = 'READY'
 ) AS ReadyCars
 ORDER BY TotalCost

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
