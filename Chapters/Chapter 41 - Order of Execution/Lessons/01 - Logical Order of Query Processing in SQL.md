---
lesson_id: C41-L01
chapter: 41
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C41-L01: Logical Order of Query Processing in SQL

## Textbook excerpt

Chapter 41: Order of Execution
Examples
Logical Order of Query Processing in SQL

 /*(8)*/ SELECT /*9*/ DISTINCT /*11*/ TOP
 /*(1)*/ FROM
 /*(3)*/         JOIN
 /*(2)*/        ON
 /*(4)*/ WHERE
 /*(5)*/ GROUP BY
 /*(6)*/ WITH {CUBE | ROLLUP}
 /*(7)*/ HAVING
 /*(10)*/ ORDER BY
 /*(11)*/ LIMIT


The order in which a query is processed and description of each section.

VT stands for 'Virtual Table' and shows how various data is produced as the query is processed

   1. FROM: A Cartesian product (cross join) is performed between the first two tables in the
      FROM clause, and as a result, virtual table VT1 is generated.

   2. ON: The ON filter is applied to VT1. Only rows for which the is TRUE are inserted to VT2.

   3. OUTER (join): If an OUTER JOIN is specified (as opposed to a CROSS JOIN or an INNER
      JOIN), rows from the preserved table or tables for which a match was not found are added to
      the rows from VT2 as outer rows, generating VT3. If more than two tables appear in the
      FROM clause, steps 1 through 3 are applied repeatedly between the result of the last join
      and the next table in the FROM clause until all tables are processed.

   4. WHERE: The WHERE filter is applied to VT3. Only rows for which the is TRUE are inserted
      to VT4.

   5. GROUP BY: The rows from VT4 are arranged in groups based on the column list specified in
      the GROUP BY clause. VT5 is generated.

   6. CUBE | ROLLUP: Supergroups (groups of groups) are added to the rows from VT5,
      generating VT6.

   7. HAVING: The HAVING filter is applied to VT6. Only groups for which the is TRUE are
      inserted to VT7.

   8. SELECT: The SELECT list is processed, generating VT8.

   9. DISTINCT: Duplicate rows are removed from VT8. VT9 is generated.

  10. ORDER BY: The rows from VT9 are sorted according to the column list specified in the



      ORDER BY clause. A cursor is generated (VC10).

  11. TOP: The specified number or percentage of rows is selected from the beginning of VC10.
      Table VT11 is generated and returned to the caller. LIMIT has the same functionality as TOP
      in some SQL dialects such as Postgres and Netezza.

Read Order of Execution online: https://riptutorial.com/sql/topic/3671/order-of-execution

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
