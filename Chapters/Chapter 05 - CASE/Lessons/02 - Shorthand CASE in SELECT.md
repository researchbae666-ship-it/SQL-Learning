---
lesson_id: C05-L02
chapter: 5
lesson: 2
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C05-L02: Shorthand CASE in SELECT

**Chapter:** 5 · **Lesson:** 2 of 6 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Shorthand CASE in SELECT

CASE's shorthand variant evaluates an expression (usually a column) against a series of values.
This variant is a bit shorter, and saves repeating the evaluated expression over and over again.
The ELSE clause can still be used, though:

 SELECT Id, ItemId, Price,
   CASE Price WHEN 5 THEN 'CHEAP'
              WHEN 15 THEN 'AFFORDABLE'
              ELSE         'EXPENSIVE'
   END as PriceRating
 FROM ItemSales


A word of caution. It's important to realize that when using the short variant the entire statement is
evaluated at each WHEN. Therefore the following statement:

 SELECT
     CASE ABS(CHECKSUM(NEWID())) % 4
         WHEN 0 THEN 'Dr'
         WHEN 1 THEN 'Master'
         WHEN 2 THEN 'Mr'
         WHEN 3 THEN 'Mrs'
     END


may produce a NULL result. That is because at each WHEN NEWID() is being called again with a new
result. Equivalent to:

 SELECT
     CASE
           WHEN ABS(CHECKSUM(NEWID())) % 4 = 0 THEN 'Dr'
           WHEN ABS(CHECKSUM(NEWID())) % 4 = 1 THEN 'Master'
           WHEN ABS(CHECKSUM(NEWID())) % 4 = 2 THEN 'Mr'
           WHEN ABS(CHECKSUM(NEWID())) % 4 = 3 THEN 'Mrs'
     END


Therefore it can miss all the WHEN cases and result as NULL.

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
