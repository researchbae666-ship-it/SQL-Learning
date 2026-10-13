---
lesson_id: C05-L04
chapter: 5
lesson: 4
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C05-L04: Using CASE in UPDATE

**Chapter:** 5 · **Lesson:** 4 of 6 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Using CASE in UPDATE

sample on price increases:

 UPDATE ItemPrice
 SET Price = Price *
   CASE ItemId
     WHEN 1 THEN 1.05
     WHEN 2 THEN 1.10
     WHEN 3 THEN 1.15
     ELSE 1.00
   END

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
