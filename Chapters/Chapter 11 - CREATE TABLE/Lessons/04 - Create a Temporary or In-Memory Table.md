---
lesson_id: C11-L04
chapter: 11
lesson: 4
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C11-L04: Create a Temporary or In-Memory Table

**Chapter:** 11 · **Lesson:** 4 of 4 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Create a Temporary or In-Memory Table


PostgreSQL and SQLite
To create a temporary table local to the session:

 CREATE TEMP TABLE MyTable(...);





SQL Server
To create a temporary table local to the session:

 CREATE TABLE #TempPhysical(...);


To create a temporary table visible to everyone:

 CREATE TABLE ##TempPhysicalVisibleToEveryone(...);


To create an in-memory table:

 DECLARE @TempMemory TABLE(...);


Read CREATE TABLE online: https://riptutorial.com/sql/topic/348/create-table

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
