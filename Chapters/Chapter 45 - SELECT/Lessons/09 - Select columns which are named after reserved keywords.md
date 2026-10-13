---
lesson_id: C45-L09
chapter: 45
lesson: 9
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C45-L09: Select columns which are named after reserved keywords

## Textbook excerpt

Select columns which are named after reserved keywords

When a column name matches a reserved keyword, standard SQL requires that you enclose it in
double quotation marks:

 SELECT
     "ORDER",
     ID
 FROM ORDERS


Note that it makes the column name case-sensitive.

Some DBMSes have proprietary ways of quoting names. For example, SQL Server uses square
brackets for this purpose:

 SELECT
     [Order],
     ID




 FROM ORDERS


while MySQL (and MariaDB) by default use backticks:

 SELECT
     `Order`,
     id
 FROM orders

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
