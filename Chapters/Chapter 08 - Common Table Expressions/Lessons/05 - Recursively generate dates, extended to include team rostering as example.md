---
lesson_id: C08-L05
chapter: 8
lesson: 5
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C08-L05: Recursively generate dates, extended to include team rostering as example

**Chapter:** 8 · **Lesson:** 5 of 6 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Recursively generate dates, extended to include team rostering as example

 DECLARE @DateFrom DATETIME = '2016-06-01 06:00'
 DECLARE @DateTo DATETIME = '2016-07-01 06:00'
 DECLARE @IntervalDays INT = 7

 -- Transition Sequence = Rest & Relax into Day Shift into Night Shift
 -- RR (Rest & Relax) = 1
 -- DS (Day Shift) = 2
 -- NS (Night Shift) = 3

 ;WITH roster AS
 (
    SELECT @DateFrom AS RosterStart, 1 AS TeamA, 2 AS TeamB, 3 AS TeamC
    UNION ALL
    SELECT DATEADD(d, @IntervalDays, RosterStart),
           CASE TeamA WHEN 1 THEN 2 WHEN 2 THEN 3 WHEN 3 THEN 1 END AS TeamA,
           CASE TeamB WHEN 1 THEN 2 WHEN 2 THEN 3 WHEN 3 THEN 1 END AS TeamB,
           CASE TeamC WHEN 1 THEN 2 WHEN 2 THEN 3 WHEN 3 THEN 1 END AS TeamC
    FROM roster WHERE RosterStart < DATEADD(d, -@IntervalDays, @DateTo)
 )

 SELECT RosterStart,
        ISNULL(LEAD(RosterStart) OVER (ORDER BY RosterStart), RosterStart + @IntervalDays) AS





 RosterEnd,
        CASE TeamA WHEN 1 THEN 'RR' WHEN 2 THEN 'DS' WHEN 3 THEN 'NS' END AS TeamA,
        CASE TeamB WHEN 1 THEN 'RR' WHEN 2 THEN 'DS' WHEN 3 THEN 'NS' END AS TeamB,
        CASE TeamC WHEN 1 THEN 'RR' WHEN 2 THEN 'DS' WHEN 3 THEN 'NS' END AS TeamC
 FROM roster


Result

I.e. For Week 1 TeamA is on R&R, TeamB is on Day Shift and TeamC is on Night Shift.

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
