---
lesson_id: C22-L02
chapter: 22
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C22-L02: Use IN to return rows with a value contained in a list

## Textbook excerpt

Use IN to return rows with a value contained in a list

This example uses the Car Table from the Example Databases.

 SELECT *
 FROM Cars
 WHERE TotalCost IN (100, 200, 300)


This query will return Car #2 which costs 200 and Car #3 which costs 100. Note that this is
equivalent to using multiple clauses with OR, e.g.:

 SELECT *
 FROM Cars
 WHERE TotalCost = 100 OR TotalCost = 200 OR TotalCost = 300

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
