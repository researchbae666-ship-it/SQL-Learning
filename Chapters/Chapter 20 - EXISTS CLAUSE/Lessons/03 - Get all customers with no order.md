---
lesson_id: C20-L03
chapter: 20
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C20-L03: Get all customers with no order

## Textbook excerpt

Get all customers with no order
 SELECT * FROM Customer WHERE NOT EXISTS (
     SELECT * FROM Order WHERE Order.CustomerId = Customer.Id
 )




Result

 Id     FirstName     LastName

 1      Ozgur         Ozturk

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
