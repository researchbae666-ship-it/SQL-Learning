---
lesson_id: C25-L04
chapter: 25
lesson: 4
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C25-L04: List Concatenation

## Textbook excerpt

List Concatenation

Partial credit to this SO answer.

List Concatenation aggregates a column or expression by combining the values into a single string
for each group. A string to delimit each value (either blank or a comma when omitted) and the
order of the values in the result can be specified. While it is not part of the SQL standard, every
major relational database vendor supports it in their own way.


MySQL
 SELECT ColumnA
      , GROUP_CONCAT(ColumnB ORDER BY ColumnB SEPARATOR ',') AS ColumnBs
   FROM TableName
  GROUP BY ColumnA
  ORDER BY ColumnA;




Oracle & DB2
 SELECT ColumnA
      , LISTAGG(ColumnB, ',') WITHIN GROUP (ORDER BY ColumnB) AS ColumnBs
   FROM TableName
  GROUP BY ColumnA
  ORDER BY ColumnA;




PostgreSQL
 SELECT ColumnA
      , STRING_AGG(ColumnB, ',' ORDER BY ColumnB) AS ColumnBs
   FROM TableName
  GROUP BY ColumnA
  ORDER BY ColumnA;




SQL Server

SQL Server 2016 and earlier
(CTE included to encourage the DRY principle)

   WITH CTE_TableName AS (
        SELECT ColumnA, ColumnB
          FROM TableName)
 SELECT t0.ColumnA
      , STUFF((
        SELECT ',' + t1.ColumnB
          FROM CTE_TableName t1
         WHERE t1.ColumnA = t0.ColumnA
         ORDER BY t1.ColumnB
           FOR XML PATH('')), 1, 1, '') AS ColumnBs
   FROM CTE_TableName t0
  GROUP BY t0.ColumnA
  ORDER BY ColumnA;



SQL Server 2017 and SQL Azure

 SELECT ColumnA
      , STRING_AGG(ColumnB, ',') WITHIN GROUP (ORDER BY ColumnB) AS ColumnBs
   FROM TableName
  GROUP BY ColumnA
  ORDER BY ColumnA;




SQLite
without ordering:

 SELECT ColumnA
      , GROUP_CONCAT(ColumnB, ',') AS ColumnBs
   FROM TableName
  GROUP BY ColumnA
  ORDER BY ColumnA;


ordering requires a subquery or CTE:

   WITH CTE_TableName AS (
        SELECT ColumnA, ColumnB
          FROM TableName
         ORDER BY ColumnA, ColumnB)
 SELECT ColumnA
      , GROUP_CONCAT(ColumnB, ',') AS ColumnBs
   FROM CTE_TableName
  GROUP BY ColumnA
  ORDER BY ColumnA;

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
