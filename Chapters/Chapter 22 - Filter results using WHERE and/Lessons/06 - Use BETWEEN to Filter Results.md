---
lesson_id: C22-L06
chapter: 22
lesson: 6
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C22-L06: Use BETWEEN to Filter Results

## Textbook excerpt

Use BETWEEN to Filter Results

The following examples use the Item Sales and Customers sample databases.

      Note: The BETWEEN operator is inclusive.

Using the BETWEEN operator with Numbers:

 SELECT * From ItemSales
 WHERE Quantity BETWEEN 10 AND 17


This query will return all ItemSales records that have a quantity that is greater or equal to 10 and
less than or equal to 17. The results will look like:

 Id   SaleDate        ItemId   Quantity   Price

 1    2013-07-01      100      10         34.5

 4    2013-07-23      100      15         34.5

 5    2013-07-24      145      10         34.5




Using the BETWEEN operator with Date Values:

 SELECT * From ItemSales
 WHERE SaleDate BETWEEN '2013-07-11' AND '2013-05-24'


This query will return all ItemSales records with a SaleDate that is greater than or equal to July 11,
2013 and less than or equal to May 24, 2013.

 Id   SaleDate       ItemId   Quantity    Price

 3    2013-07-11     100      20          34.5

 4    2013-07-23     100      15          34.5

 5    2013-07-24     145      10          34.5

      When comparing datetime values instead of dates, you may need to convert the
      datetime values into a date values, or add or subtract 24 hours to get the correct
      results.


Using the BETWEEN operator with Text Values:

 SELECT Id, FName, LName FROM Customers
 WHERE LName BETWEEN 'D' AND 'L';


Live example: SQL fiddle

This query will return all customers whose name alphabetically falls between the letters 'D' and 'L'.
In this case, Customer #1 and #3 will be returned. Customer #2, whose name begins with a 'M' will
not be included.

 Id   FName      LName

 1    William    Jones

 3    Richard    Davis

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
