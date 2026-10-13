---
lesson_id: C20-L02
chapter: 20
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C20-L02: Get all customers with a least one order

## Textbook excerpt

Get all customers with a least one order
 SELECT * FROM Customer WHERE EXISTS (
     SELECT * FROM Order WHERE Order.CustomerId=Customer.Id
 )


Result

 Id   FirstName      LastName

 2    Youssef        Medi

 3    Henry          Tai

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
