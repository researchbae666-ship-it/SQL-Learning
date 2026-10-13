---
lesson_id: C22-L05
chapter: 22
lesson: 5
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C22-L05: Use HAVING with Aggregate Functions

## Textbook excerpt

Use HAVING with Aggregate Functions

Unlike the WHERE clause, HAVING can be used with aggregate functions.

      An aggregate function is a function where the values of multiple rows are grouped
      together as input on certain criteria to form a single value of more significant meaning
      or measurement (Wikipedia).

Common aggregate functions include COUNT(), SUM(), MIN(), and MAX().


This example uses the Car Table from the Example Databases.

 SELECT CustomerId, COUNT(Id) AS [Number of Cars]
 FROM Cars
 GROUP BY CustomerId
 HAVING COUNT(Id) > 1


This query will return the CustomerId and Number of Cars count of any customer who has more than
one car. In this case, the only customer who has more than one car is Customer #1.

The results will look like:

 CustomerId       Number of Cars

 1                2

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
