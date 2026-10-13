---
lesson_id: C32-L11
chapter: 32
lesson: 11
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C32-L11: Partial or Filtered Index

## Textbook excerpt

Partial or Filtered Index

SQL Server and SQLite allow to create indexes that contain not only a subset of columns, but also
a subset of rows.

Consider a constant growing amount of orders with order_state_id equal to finished (2), and a
stable amount of orders with order_state_id equal to started (1).

If your business make use of queries like this:

 SELECT id, comment
   FROM orders
  WHERE order_state_id = 1
    AND product_id = @some_value;


Partial indexing allows you to limit the index, including only the unfinished orders:

 CREATE INDEX Started_Orders
           ON orders(product_id)
        WHERE order_state_id = 1;


This index will be smaller than an unfiltered index, which saves space and reduces the cost of
updating the index.

Read Indexes online: https://riptutorial.com/sql/topic/344/indexes

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
