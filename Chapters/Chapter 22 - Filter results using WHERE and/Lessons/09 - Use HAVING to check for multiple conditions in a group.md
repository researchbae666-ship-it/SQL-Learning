---
lesson_id: C22-L09
chapter: 22
lesson: 9
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C22-L09: Use HAVING to check for multiple conditions in a group

## Textbook excerpt

Use HAVING to check for multiple conditions in a group

Orders Table

 CustomerId       ProductId    Quantity   Price

 1                2            5          100

 1                3            2          200

 1                4            1          500

 2                1            4          50

 3                5            6          700

To check for customers who have ordered both - ProductID 2 and 3, HAVING can be used

  select customerId
  from orders
  where productID in (2,3)
  group by customerId
  having count(distinct productID) = 2


Return value:

 customerId

 1

The query selects only records with the productIDs in questions and with the HAVING clause
checks for groups having 2 productIds and not just one.

Another possibility would be

  select customerId
  from orders
  group by customerId
  having sum(case when productID = 2 then 1 else 0 end) > 0




     and sum(case when productID = 3 then 1 else 0 end) > 0


This query selects only groups having at least one record with productID 2 and at least one with
productID 3.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
