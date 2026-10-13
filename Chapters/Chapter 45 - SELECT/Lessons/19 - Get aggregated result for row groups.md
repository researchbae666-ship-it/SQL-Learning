---
lesson_id: C45-L19
chapter: 45
lesson: 19
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C45-L19: Get aggregated result for row groups

## Textbook excerpt

Get aggregated result for row groups

Counting rows based on a specific column value:

 SELECT category, COUNT(*) AS item_count
 FROM item
 GROUP BY category;




Getting average income by department:

 SELECT department, AVG(income)
 FROM employees
 GROUP BY department;


The important thing is to select only columns specified in the GROUP BY clause or used with
aggregate functions.


There WHERE clause can also be used with GROUP BY, but WHERE filters out records before any
grouping is done:

 SELECT department, AVG(income)
 FROM employees
 WHERE department <> 'ACCOUNTING'
 GROUP BY department;


If you need to filter the results after the grouping has been done, e.g, to see only departments
whose average income is larger than 1000, you need to use the HAVING clause:

 SELECT department, AVG(income)
 FROM employees
 WHERE department <> 'ACCOUNTING'
 GROUP BY department
 HAVING avg(income) > 1000;

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
