---
lesson_id: C60-L02
chapter: 60
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C60-L02: Simple explanation and Example

## Textbook excerpt

Simple explanation and Example

In simple terms:

      • UNION joins 2 result sets while removing duplicates from the result set
      • UNION ALL joins 2 result sets without attempting to remove duplicates

        One mistake many people make is to use a UNION when they do not need to have the
        duplicates removed. The additional performance cost against large results sets can be
        very significant.




When you might need UNION

Suppose you need to filter a table against 2 different attributes, and you have created separate
non-clustered indexes for each column. A UNION enables you to leverage both indexes while still
preventing duplicates.

 SELECT C1, C2, C3 FROM Table1 WHERE C1 = @Param1
 UNION
 SELECT C1, C2, C3 FROM Table1 WHERE C2 = @Param2


This simplifies your performance tuning since only simple indexes are needed to perform these
queries optimally. You may even be able to get by with quite a bit fewer non-clustered indexes
improving overall write performance against the source table as well.

When you might need UNION ALL

Suppose you still need to filter a table against 2 attributes, but you do not need to filter duplicate
records (either because it doesn't matter or your data wouldn't produce any duplicates during the
union due to your data model design).

 SELECT C1 FROM Table1
 UNION ALL
 SELECT C1 FROM Table2


This is especially useful when creating Views that join data that is designed to be physically
partitioned across multiple tables (maybe for performance reasons, but still wants to roll-up
records). Since the data is already split, having the database engine remove duplicates adds no
value and just adds additional processing time to the queries.

Read UNION / UNION ALL online: https://riptutorial.com/sql/topic/349/union---union-all

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
