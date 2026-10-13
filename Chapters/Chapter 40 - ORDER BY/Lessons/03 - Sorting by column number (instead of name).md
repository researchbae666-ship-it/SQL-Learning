---
lesson_id: C40-L03
chapter: 40
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C40-L03: Sorting by column number (instead of name)

## Textbook excerpt

Sorting by column number (instead of name)

You can use a column's number (where the leftmost column is '1') to indicate which column to
base the sort on, instead of describing the column by its name.

Pro: If you think it's likely you might change column names later, doing so won't break this code.

Con: This will generally reduce readability of the query (It's instantly clear what 'ORDER BY
Reputation' means, while 'ORDER BY 14' requires some counting, probably with a finger on the
screen.)

This query sorts result by the info in relative column position 3 from select statement instead of
column name Reputation.



 SELECT DisplayName, JoinDate, Reputation
 FROM Users
 ORDER BY 3



 DisplayName       JoinDate      Reputation

 Community         2008-09-15    1

 Jarrod Dixon      2008-10-03    11739

 Geoff Dalgas      2008-10-03    12567

 Joel Spolsky      2008-09-16    25784

 Jeff Atwood       2008-09-16    37628

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
