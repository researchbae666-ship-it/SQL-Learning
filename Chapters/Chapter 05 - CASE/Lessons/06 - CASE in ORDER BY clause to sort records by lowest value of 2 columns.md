---
lesson_id: C05-L06
chapter: 5
lesson: 6
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C05-L06: CASE in ORDER BY clause to sort records by lowest value of 2 columns

**Chapter:** 5 · **Lesson:** 6 of 6 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

CASE in ORDER BY clause to sort records by lowest value of 2 columns

Imagine that you need sort records by lowest value of either one of two columns. Some databases
could use a non-aggregated MIN() or LEAST() function for this (... ORDER BY MIN(Date1, Date2)), but
in standard SQL, you have to use a CASE expression.

The CASE expression in the query below looks at the Date1 and Date2 columns, checks which
column has the lower value, and sorts the records depending on this value.


Sample data
 Id    Date1          Date2

 1     2017-01-01     2017-01-31

 2     2017-01-31     2017-01-03

 3     2017-01-31     2017-01-02

 4     2017-01-06     2017-01-31

 5     2017-01-31     2017-01-05

 6     2017-01-04     2017-01-31


Query
 SELECT Id, Date1, Date2
 FROM YourTable
 ORDER BY CASE
            WHEN COALESCE(Date1, '1753-01-01') < COALESCE(Date2, '1753-01-01') THEN Date1
            ELSE Date2
          END




Results
 Id   Date1          Date2

 1    2017-01-01     2017-01-31

 3    2017-01-31     2017-01-02

 2    2017-01-31     2017-01-03

 6    2017-01-04     2017-01-31

 5    2017-01-31     2017-01-05

 4    2017-01-06     2017-01-31



Explanation
As you see row with Id = 1 is first, that because Date1 have lowest record from entire table 2017-
01-01, row where Id = 3 is second that because Date2 equals to 2017-01-02 that is second lowest
value from table and so on.

So we have sorted records from 2017-01-01 to 2017-01-06 ascending and no care on which one
column Date1 or Date2 are those values.

Read CASE online: https://riptutorial.com/sql/topic/456/case

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
