---
lesson_id: C45-L04
chapter: 45
lesson: 4
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C45-L04: When Can You Use *, Bearing The Above Warning In Mind?

## Textbook excerpt

When Can You Use *, Bearing The Above Warning In Mind?

While best avoided in production code, using * is fine as a shorthand when performing manual
queries against the database for investigation or prototype work.

Sometimes design decisions in your application make it unavoidable (in such circumstances,
prefer tablealias.* over just * where possible).

When using EXISTS, such as SELECT A.col1, A.Col2 FROM A WHERE EXISTS (SELECT * FROM B where
A.ID = B.A_ID)



, we are not returning any data from B. Thus a join is unnecessary, and the engine knows no
values from B are to be returned, thus no performance hit for using *. Similarly COUNT(*) is fine as it
also doesn't actually return any of the columns, so only needs to read and process those that are
used for filtering purposes.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
