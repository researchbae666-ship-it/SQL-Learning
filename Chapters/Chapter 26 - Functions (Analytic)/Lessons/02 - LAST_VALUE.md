---
lesson_id: C26-L02
chapter: 26
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C26-L02: LAST_VALUE

## Textbook excerpt

LAST_VALUE

The LAST_VALUE function provides the last value in an ordered result set, which you specify using a
scalar expression.

 SELECT TerritoryID, StartDate, BusinessentityID,
        LAST_VALUE(BusinessentityID)
         OVER(ORDER BY TerritoryID) AS LastValue
 FROM SalesTerritoryHistory;


This example uses the LAST_VALUE function to return the last value for each rowset in the ordered
values.

 TerritoryID    StartDate                  BusinessentityID      LastValue

 1              2005-07-01 00.00.00.000    280                   283

 1              2006-11-01 00.00.00.000    284                   283

 1              2005-07-01 00.00.00.000    283                   283

 2              2007-01-01 00.00.00.000    277                   275

 2              2005-07-01 00.00.00.000    275                   275

 3              2007-01-01 00.00.00.000    275                   277

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
