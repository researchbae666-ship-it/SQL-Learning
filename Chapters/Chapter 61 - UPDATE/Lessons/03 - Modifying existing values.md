---
lesson_id: C61-L03
chapter: 61
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C61-L03: Modifying existing values

## Textbook excerpt

Modifying existing values

This example uses the Cars Table from the Example Databases.

 UPDATE Cars
 SET TotalCost = TotalCost + 100
 WHERE Id = 3 or Id = 4


Update operations can include current values in the updated row. In this simple example the
TotalCost is incremented by 100 for two rows:





   • The TotalCost of Car #3 is increased from 100 to 200
   • The TotalCost of Car #4 is increased from 1254 to 1354

A column's new value may be derived from its previous value or from any other column's value in
the same table or a joined table.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
