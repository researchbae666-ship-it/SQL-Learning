---
lesson_id: C05-L03
chapter: 5
lesson: 3
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C05-L03: CASE in a clause ORDER BY

**Chapter:** 5 · **Lesson:** 3 of 6 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

CASE in a clause ORDER BY

We can use 1,2,3.. to determine the type of order:



 SELECT * FROM DEPT
 ORDER BY
 CASE DEPARTMENT
       WHEN 'MARKETING' THEN 1
       WHEN 'SALES' THEN 2
       WHEN 'RESEARCH' THEN 3
       WHEN 'INNOVATION' THEN 4
       ELSE         5
       END,
       CITY



 ID   REGION               CITY            DEPARTMENT            EMPLOYEES_NUMBER

 12   New England          Boston          MARKETING             9

 15   West                 San Francisco   MARKETING             12

 9    Midwest              Chicago         SALES                 8

 14   Mid-Atlantic         New York        SALES                 12

 5    West                 Los Angeles     RESEARCH              11

 10   Mid-Atlantic         Philadelphia    RESEARCH              13

 4    Midwest              Chicago         INNOVATION            11

 2    Midwest              Detroit         HUMAN RESOURCES       9

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
