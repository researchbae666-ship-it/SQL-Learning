---
lesson_id: C25-L01
chapter: 25
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C25-L01: SUM

## Textbook excerpt

Chapter 25: Functions (Aggregate)
Syntax
   • Function([DISTINCT] expression) -DISTINCT is an optional parameter
   • AVG ( [ ALL | DISTINCT ] expression )
   • COUNT( { [ALL | DISTINCT ] expression ] | * } )
   • GROUPING(<column_expression>)
   • MAX ( [ ALL | DISTINCT ] expression )
   • MIN ( [ ALL | DISTINCT ] expression )
   • SUM ( [ ALL | DISTINCT ] expression )
   • VAR ( [ ALL | DISTINCT ] expression )
     OVER ( [ partition_by_clause ] order_by_clause )
   • VARP ( [ ALL | DISTINCT ] expression )
     OVER ( [ partition_by_clause ] order_by_clause
   • STDEV ( [ ALL | DISTINCT ] expression )
     OVER ( [ partition_by_clause ] order_by_clause )
   • STDEVP ( [ ALL | DISTINCT ] expression )
     OVER ( [ partition_by_clause ] order_by_clause )


Remarks
In database management an aggregate function is a function where the values of multiple rows
are grouped together as input on certain criteria to form a single value of more significant meaning
or measurement such as a set, a bag or a list.

 MIN         returns the smallest value in a given column
 MAX         returns the largest value in a given column
 SUM         returns the sum of the numeric values in a given column
 AVG         returns the average value of a given column
 COUNT       returns the total number of values in a given column
 COUNT(*)    returns the number of rows in a table
 GROUPING    Is a column or an expression that contains a column in a GROUP BY clause.
 STDEV       returns the statistical standard deviation of all values in the specified
 expression.
 STDEVP      returns the statistical standard deviation for the population for all values in the
 specified expression.
 VAR         returns the statistical variance of all values in the specified expression. may be
 followed by the OVER clause.
 VARP        returns the statistical variance for the population for all values in the specified
 expression.


      Aggregate functions are used to compute against a "returned column of numeric data"
      from your SELECT statement. They basically summarize the results of a particular
      column of selected data. - SQLCourse2.com

All aggregate functions ignore NULL values.




Examples
SUM

Sum function sum the value of all the rows in the group. If the group by clause is omitted then sums
all the rows.

 select sum(salary) TotalSalary
 from employees;



 TotalSalary

 2500

 select DepartmentId, sum(salary) TotalSalary
 from employees
 group by DepartmentId;



 DepartmentId       TotalSalary

 1                  2000

 2                  500

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
