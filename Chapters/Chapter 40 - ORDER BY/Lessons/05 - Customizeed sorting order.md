---
lesson_id: C40-L05
chapter: 40
lesson: 5
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C40-L05: Customizeed sorting order

## Textbook excerpt

Customizeed sorting order

To sort this table Employee by department, you would use ORDER BY Department. However, if you want
a different sort order that is not alphabetical, you have to map the Department values into different
values that sort correctly; this can be done with a CASE expression:

 Name      Department

 Hasan     IT

 Yusuf     HR

 Hillary   HR

 Joe       IT

 Merry     HR



 Name      Department

 Ken       Accountant

 SELECT *
 FROM Employee
 ORDER BY CASE Department
          WHEN 'HR'         THEN 1
          WHEN 'Accountant' THEN 2
          ELSE                   3
          END;



 Name      Department

 Yusuf     HR

 Hillary   HR

 Merry     HR

 Ken       Accountant

 Hasan     IT

 Joe       IT

Read ORDER BY online: https://riptutorial.com/sql/topic/620/order-by

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
