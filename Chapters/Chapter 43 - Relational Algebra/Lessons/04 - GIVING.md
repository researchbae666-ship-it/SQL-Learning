---
lesson_id: C43-L04
chapter: 43
lesson: 4
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C43-L04: GIVING

## Textbook excerpt

GIVING
Relational expressions can be chained together by naming the individual expressions using the
giving keyword, or by embedding one expression within another.

< relational algebra expression > giving < alias name >

For example, consider the following expressions:
select People where DepartmentID = 2 giving A
project A over PersonName giving B

This will result in table B below, with table A being the result of the first expression.




The first expression is evaluated and the resulting table is given the alias A. This table is then
used within the second expression to give the final table with an alias of B.

Another way of writing this expression is to replace the table alias name in the second expression
with the entire text of the first expression enclosed within brackets:
project (select People where DepartmentID = 2) over PersonName giving B

This is called a nested expression.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
