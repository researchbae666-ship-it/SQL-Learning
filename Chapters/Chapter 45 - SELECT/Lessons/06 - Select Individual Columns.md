---
lesson_id: C45-L06
chapter: 45
lesson: 6
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C45-L06: Select Individual Columns

## Textbook excerpt

Select Individual Columns

 SELECT
     PhoneNumber,
     Email,
     PreferredContact
 FROM Customers


This statement will return the columns PhoneNumber, Email, and PreferredContact from all rows of the
Customers table. Also the columns will be returned in the sequence in which they appear in the
SELECT clause.


The result will be:

 PhoneNumber          Email                         PreferredContact

 3347927472           william.jones@example.com     PHONE

 2137921892           dmiller@example.net           EMAIL

 NULL                 richard0123@example.com       EMAIL

If multiple tables are joined together, you can select columns from specific tables by specifying the
table name before the column name: [table_name].[column_name]





 SELECT
      Customers.PhoneNumber,
      Customers.Email,
      Customers.PreferredContact,
      Orders.Id AS OrderId
 FROM
      Customers
 LEFT JOIN
      Orders ON Orders.CustomerId = Customers.Id


*AS OrderId means that the Id field of Orders table will be returned as a column named OrderId. See
selecting with column alias for further information.

To avoid using long table names, you can use table aliases. This mitigates the pain of writing long
table names for each field that you select in the joins. If you are performing a self join (a join
between two instances of the same table), then you must use table aliases to distinguish your
tables. We can write a table alias like Customers c or Customers AS c. Here c works as an alias for
Customers and we can select let's say Email like this: c.Email.


 SELECT
      c.PhoneNumber,
      c.Email,
      c.PreferredContact,
      o.Id AS OrderId
 FROM
      Customers c
 LEFT JOIN
      Orders o ON o.CustomerId = c.Id

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
