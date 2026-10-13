---
lesson_id: C45-L10
chapter: 45
lesson: 10
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C45-L10: Selecting specified number of records

## Textbook excerpt

Selecting specified number of records

The SQL 2008 standard defines the FETCH FIRST clause to limit the number of records returned.

 SELECT Id, ProductName, UnitPrice, Package
 FROM Product
 ORDER BY UnitPrice DESC
 FETCH FIRST 10 ROWS ONLY


This standard is only supported in recent versions of some RDMSs. Vendor-specific non-standard
syntax is provided in other systems. Progress OpenEdge 11.x also supports the FETCH FIRST <n>
ROWS ONLY syntax.


Additionally, OFFSET <m> ROWS before FETCH FIRST <n> ROWS ONLY allows skipping rows before fetching
rows.

 SELECT Id, ProductName, UnitPrice, Package
 FROM Product
 ORDER BY UnitPrice DESC
 OFFSET 5 ROWS
 FETCH FIRST 10 ROWS ONLY


The following query is supported in SQL Server and MS Access:

 SELECT TOP 10 Id, ProductName, UnitPrice, Package
 FROM Product
 ORDER BY UnitPrice DESC


To do the same in MySQL or PostgreSQL the LIMIT keyword must be used:

 SELECT Id, ProductName, UnitPrice, Package
 FROM Product
 ORDER BY UnitPrice DESC
 LIMIT 10


In Oracle the same can be done with ROWNUM:

 SELECT Id, ProductName, UnitPrice, Package
 FROM Product
 WHERE ROWNUM <= 10
 ORDER BY UnitPrice DESC





Results: 10 records.

 Id    ProductName                UnitPrice               Package
 38    Côte de Blaye              263.50                  12 - 75 cl bottles
 29    Thüringer Rostbratwurst    123.79                  50 bags x 30 sausgs.
 9    Mishi Kobe Niku             97.00                   18 - 500 g pkgs.
 20    Sir Rodney's Marmalade     81.00                   30 gift boxes
 18    Carnarvon Tigers           62.50                   16 kg pkg.
 59    Raclette Courdavault       55.00                   5 kg pkg.
 51    Manjimup Dried Apples      53.00                   50 - 300 g pkgs.
 62    Tarte au sucre             49.30                   48 pies
 43    Ipoh Coffee                46.00                   16 - 500 g tins
 28    Rössle Sauerkraut          45.60                   25 - 825 g cans


Vendor Nuances:

It is important to note that the TOP in Microsoft SQL operates after the WHERE clause and will return
the specified number of results if they exist anywhere in the table, while ROWNUM works as part of the
WHERE clause so if other conditions do not exist in the specified number of rows at the beginning of
the table, you will get zero results when there could be others to be found.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
