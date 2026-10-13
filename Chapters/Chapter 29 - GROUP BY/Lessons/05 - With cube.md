---
lesson_id: C29-L05
chapter: 29
lesson: 5
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C29-L05: With cube

## Textbook excerpt

With cube

 select Food,Brand,Total_amount
 from Table
 group by Food,Brand,Total_amount with cube



 Food     Brand      Total_amount

 Pasta    Brand1     100

 Pasta    Brand2     250

 Pasta    ALL        350

 Pizza    Brand2     300

 Pizza    ALL        300

 ALL      Brand1     100

 ALL      Brand2     550

 ALL      ALL        650

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
