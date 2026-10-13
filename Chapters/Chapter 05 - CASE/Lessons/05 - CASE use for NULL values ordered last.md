---
lesson_id: C05-L05
chapter: 5
lesson: 5
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C05-L05: CASE use for NULL values ordered last

**Chapter:** 5 · **Lesson:** 5 of 6 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

CASE use for NULL values ordered last

in this way '0' representing the known values are ranked first, '1' representing the NULL values are
sorted by the last:

 SELECT ID
       ,REGION
       ,CITY
       ,DEPARTMENT
       ,EMPLOYEES_NUMBER




     FROM DEPT
     ORDER BY
     CASE WHEN REGION IS NULL THEN 1
     ELSE 0
     END,
     REGION



 ID    REGION              CITY            DEPARTMENT            EMPLOYEES_NUMBER

 10    Mid-Atlantic        Philadelphia    RESEARCH              13

 14    Mid-Atlantic        New York        SALES                 12

 9     Midwest             Chicago         SALES                 8

 12    New England         Boston          MARKETING             9

 5     West                Los Angeles     RESEARCH              11

 15    NULL                San Francisco   MARKETING             12

 4     NULL                Chicago         INNOVATION            11

 2     NULL                Detroit         HUMAN RESOURCES       9

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
