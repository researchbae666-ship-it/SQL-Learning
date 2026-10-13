---
lesson_id: C32-L01
chapter: 32
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C32-L01: Creating an Index

## Textbook excerpt

Chapter 32: Indexes
Introduction
Indexes are a data structure that contains pointers to the contents of a table arranged in a specific
order, to help the database optimize queries. They are similar to the index of book, where the
pages (rows of the table) are indexed by their page number.

Several types of indexes exist, and can be created on a table. When an index exists on the
columns used in a query's WHERE clause, JOIN clause, or ORDER BY clause, it can substantially
improve query performance.


Remarks
Indexes are a way of speeding up read queries by sorting the rows of a table according to a
column.

The effect of an index is not noticeable for small databases like the example, but if there are a
large number of rows, it can greatly improve performance. Instead of checking every row of the
table, the server can do a binary search on the index.

The tradeoff for creating an index is write speed and database size. Storing the index takes space.
Also, every time an INSERT is done or the column is updated, the index must be updated. This is
not as expensive an operation as scanning the entire table on a SELECT query, but it is still
something to keep in mind.


Examples
Creating an Index

 CREATE INDEX ix_cars_employee_id ON Cars (EmployeeId);


This will create an index for the column EmployeeId in the table Cars. This index will improve the
speed of queries asking the server to sort or select by values in EmployeeId, such as the
following:

 SELECT * FROM Cars WHERE EmployeeId = 1


The index can contain more than 1 column, as in the following;

 CREATE INDEX ix_cars_e_c_o_ids ON Cars (EmployeeId, CarId, OwnerId);


In this case, the index would be useful for queries asking to sort or select by all included columns,
if the set of conditions is ordered in the same way. That means that when retrieving the data, it can



find the rows to retrieve using the index, instead of looking through the full table.

For example, the following case would utilize the second index;

 SELECT * FROM Cars WHERE EmployeeId = 1 Order by CarId DESC


If the order differs, however, the index does not have the same advantages, as in the following;

 SELECT * FROM Cars WHERE OwnerId = 17 Order by CarId DESC


The index is not as helpful because the database must retrieve the entire index, across all values
of EmployeeId and CarID, in order to find which items have OwnerId = 17.

(The index may still be used; it may be the case that the query optimizer finds that retrieving the
index and filtering on the OwnerId, then retrieving only the needed rows is faster than retrieving the
full table, especially if the table is large.)

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
