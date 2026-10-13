---
lesson_id: C63-L03
chapter: 63
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C63-L03: Getting a running total

## Textbook excerpt

Getting a running total

Given this data:

 date             amount

 2016-03-12       200

 2016-03-11       -50

 2016-03-14       100

 2016-03-15       100

 2016-03-10       -250

 SELECT date, amount, SUM(amount) OVER (ORDER BY date ASC) AS running
 FROM operations
 ORDER BY date ASC


will give you

 date             amount    running

 2016-03-10       -250      -250

 2016-03-11       -50       -300

 2016-03-12       200       -100


 date             amount   running

 2016-03-14       100      0

 2016-03-15       100      -100

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
