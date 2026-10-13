---
lesson_id: C31-L02
chapter: 31
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C31-L02: Using IN clause with a subquery

## Textbook excerpt

Using IN clause with a subquery

 SELECT *
 FROM customers
 WHERE id IN (
     SELECT DISTINCT customer_id
     FROM orders
 );


The above will give you all the customers that have orders in the system.

Read IN clause online: https://riptutorial.com/sql/topic/3169/in-clause

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
