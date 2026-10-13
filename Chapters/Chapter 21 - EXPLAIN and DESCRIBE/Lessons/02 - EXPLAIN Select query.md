---
lesson_id: C21-L02
chapter: 21
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C21-L02: EXPLAIN Select query

## Textbook excerpt

EXPLAIN Select query

An Explain infront of a select query shows you how the query will be executed. This way you to
see if the query uses an index or if you could optimize your query by adding an index.

Example query:

 explain select * from user join data on user.test = data.fk_user;


Example result:

 id select_type     table   type     possible_keys   key     key_len ref       rows   Extra
 1   SIMPLE         user    index    test            test    5       (null)    1      Using where;
 Using index
 1   SIMPLE         data    ref      fk_user         fk_user 5       user.test 1      (null)


on type you see if an index was used. In the column possible_keys you see if the execution plan
can choose from different indexes of if none exists. key tells you the acutal used index. key_len
shows you the size in bytes for one index item. The lower this value is the more index items fit into
the same memory size an they can be faster processed. rows shows you the expected number of
rows the query needs to scan, the lower the better.

Read EXPLAIN and DESCRIBE online: https://riptutorial.com/sql/topic/2928/explain-and-describe

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
