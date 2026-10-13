---
lesson_id: C29-L06
chapter: 29
lesson: 6
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C29-L06: With roll up

## Textbook excerpt

With roll up



 select Food,Brand,Total_amount
 from Table
 group by Food,Brand,Total_amount with roll up



 Food     Brand      Total_amount

 Pasta    Brand1     100

 Pasta    Brand2     250

 Pizza    Brand2     300

 Pasta    ALL        350

 Pizza    ALL        300

 ALL      ALL        650

Read GROUP BY online: https://riptutorial.com/sql/topic/627/group-by

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
