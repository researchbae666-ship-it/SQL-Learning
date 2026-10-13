---
lesson_id: C35-L06
chapter: 35
lesson: 6
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C35-L06: Joining on a Subquery

## Textbook excerpt

Joining on a Subquery

Joining a subquery is often used when you want to get aggregate data from a child/details table
and display that along with records from the parent/header table. For example, you might want to
get a count of child records, an average of some numeric column in child records, or the top or
bottom row based on a date or numeric field. This example uses aliases, which arguable makes
queries easier to read when you have multiple tables involved. Here's what a fairly typical
subquery join looks like. In this case we are retrieving all rows from the parent table Purchase
Orders and retrieving only the first row for each parent record of the child table
PurchaseOrderLineItems.

 SELECT po.Id, po.PODate, po.VendorName, po.Status, item.ItemNo,
   item.Description, item.Cost, item.Price
 FROM PurchaseOrders po
 LEFT JOIN
      (
        SELECT l.PurchaseOrderId, l.ItemNo, l.Description, l.Cost, l.Price, Min(l.id) as Id
        FROM PurchaseOrderLineItems l
        GROUP BY l.PurchaseOrderId, l.ItemNo, l.Description, l.Cost, l.Price
      ) AS item ON item.PurchaseOrderId = po.Id

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
