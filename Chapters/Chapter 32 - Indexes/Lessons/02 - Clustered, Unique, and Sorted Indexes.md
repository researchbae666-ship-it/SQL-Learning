---
lesson_id: C32-L02
chapter: 32
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C32-L02: Clustered, Unique, and Sorted Indexes

## Textbook excerpt

Clustered, Unique, and Sorted Indexes

Indexes can have several characteristics that can be set either at creation, or by altering existing
indexes.

 CREATE CLUSTERED INDEX ix_clust_employee_id ON Employees(EmployeeId, Email);


The above SQL statement creates a new clustered index on Employees. Clustered indexes are
indexes that dictate the actual structure of the table; the table itself is sorted to match the structure
of the index. That means there can be at most one clustered index on a table. If a clustered index
already exists on the table, the above statement will fail. (Tables with no clustered indexes are
also called heaps.)

 CREATE UNIQUE INDEX uq_customers_email ON Customers(Email);


This will create an unique index for the column Email in the table Customers. This index, along
with speeding up queries like a normal index, will also force every email address in that column to
be unique. If a row is inserted or updated with a non-unique Email value, the insertion or update
will, by default, fail.

 CREATE UNIQUE INDEX ix_eid_desc ON Customers(EmployeeID);


This creates an index on Customers which also creates a table constraint that the EmployeeID
must be unique. (This will fail if the column is not currently unique - in this case, if there are
employees who share an ID.)

 CREATE INDEX ix_eid_desc ON Customers(EmployeeID Desc);


This creates an index that is sorted in descending order. By default, indexes (in MSSQL server, at
least) are ascending, but that can be changed.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
