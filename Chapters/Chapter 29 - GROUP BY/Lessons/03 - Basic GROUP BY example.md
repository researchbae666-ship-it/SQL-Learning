---
lesson_id: C29-L03
chapter: 29
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C29-L03: Basic GROUP BY example

## Textbook excerpt

Basic GROUP BY example

It might be easier if you think of GROUP BY as "for each" for the sake of explanation. The query
below:

 SELECT EmpID, SUM (MonthlySalary)
 FROM Employee




 GROUP BY EmpID


is saying:

"Give me the sum of MonthlySalary's for each EmpID"

So if your table looked like this:

 +-----+-------------+
 |EmpID|MonthlySalary|
 +-----+-------------+
 |1    |200          |
 +-----+-------------+
 |2    |300          |
 +-----+-------------+


Result:

 +-+---+
 |1|200|
 +-+---+
 |2|300|
 +-+---+


Sum wouldn't appear to do anything because the sum of one number is that number. On the other
hand if it looked like this:

 +-----+-------------+
 |EmpID|MonthlySalary|
 +-----+-------------+
 |1    |200          |
 +-----+-------------+
 |1    |300          |
 +-----+-------------+
 |2    |300          |
 +-----+-------------+


Result:

 +-+---+
 |1|500|
 +-+---+
 |2|300|
 +-+---+


Then it would because there are two EmpID 1's to sum together.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
