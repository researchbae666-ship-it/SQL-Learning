---
lesson_id: C14-L04
chapter: 14
lesson: 4
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C14-L04: DELETE certain rows based upon comparisons with other tables

## Textbook excerpt

DELETE certain rows based upon comparisons with other tables

It is possible to DELETE data from a table if it matches (or mismatches) certain data in other tables.

Let's assume we want to DELETEdata from Source once its loaded into Target.

 DELETE FROM Source
 WHERE EXISTS ( SELECT 1 -- specific value in SELECT doesn't matter
                FROM Target
                Where Source.ID = Target.ID )




Most common RDBMS implementations (e.g. MySQL, Oracle, PostgresSQL, Teradata) allow
tables to be joined during DELETE allowing more complex comparison in a compact syntax.

Adding complexity to original scenario, let's assume Aggregate is built from Target once a day and
does not contain the same ID but contains the same date. Let us also assume that we want to
delete data from Source only after the aggregate is populated for the day.

On MySQL, Oracle and Teradata this can be done using:

 DELETE FROM Source
 WHERE Source.ID = TargetSchema.Target.ID
        AND TargetSchema.Target.Date = AggregateSchema.Aggregate.Date


In PostgreSQL use:

 DELETE FROM Source
 USING TargetSchema.Target, AggregateSchema.Aggregate
 WHERE Source.ID = TargetSchema.Target.ID
        AND TargetSchema.Target.DataDate = AggregateSchema.Aggregate.AggDate


This essentially results in INNER JOINs between Source, Target and Aggregate. The deletion is
performed on Source when the same IDs exist in Target AND date present in Target for those IDs
also exists in Aggregate.

Same query may also be written (on MySQL, Oracle, Teradata) as:

 DELETE Source
 FROM   Source, TargetSchema.Target, AggregateSchema.Aggregate
 WHERE Source.ID = TargetSchema.Target.ID
        AND TargetSchema.Target.DataDate = AggregateSchema.Aggregate.AggDate


Explicit joins may be mentioned in Delete statements on some RDBMS implementations (e.g.
Oracle, MySQL) but not supported on all platforms (e.g. Teradata does not support them)

Comparisons can be designed to check mismatch scenarios instead of matching ones with all
syntax styles (observe NOT EXISTS below)

 DELETE FROM Source
 WHERE NOT EXISTS ( SELECT 1 -- specific value in SELECT doesn't matter
                FROM Target
                Where Source.ID = Target.ID )


Read DELETE online: https://riptutorial.com/sql/topic/1105/delete

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
