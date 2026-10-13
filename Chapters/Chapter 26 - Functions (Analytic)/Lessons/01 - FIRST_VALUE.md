---
lesson_id: C26-L01
chapter: 26
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C26-L01: FIRST_VALUE

## Textbook excerpt

Chapter 26: Functions (Analytic)
Introduction
You use analytic functions to determine values based on groups of values. For example, you can
use this type of function to determine running totals, percentages, or the top result within a group.


Syntax
   1. FIRST_VALUE ( scalar_expression ) OVER ( [ partition_by_clause ] order_by_clause [
      rows_range_clause ] )
   2. LAST_VALUE ( scalar_expression ) OVER ( [ partition_by_clause ] order_by_clause [
      rows_range_clause ] )
   3. LAG (scalar_expression [,offset] [,default]) OVER ( [ partition_by_clause ] order_by_clause )
   4. LEAD ( scalar_expression [ ,offset ] , [ default ] ) OVER ( [ partition_by_clause ]
      order_by_clause )
   5. PERCENT_RANK( ) OVER ( [ partition_by_clause ] order_by_clause )
   6. CUME_DIST( ) OVER ( [ partition_by_clause ] order_by_clause )
   7. PERCENTILE_DISC ( numeric_literal ) WITHIN GROUP ( ORDER BY
      order_by_expression [ ASC | DESC ] ) OVER ( [ <partition_by_clause> ] )
   8. PERCENTILE_CONT ( numeric_literal ) WITHIN GROUP ( ORDER BY
      order_by_expression [ ASC | DESC ] ) OVER ( [ <partition_by_clause> ] )


Examples
FIRST_VALUE

You use the FIRST_VALUE function to determine the first value in an ordered result set, which you
identify using a scalar expression.

 SELECT StateProvinceID, Name, TaxRate,
        FIRST_VALUE(StateProvinceID)
         OVER(ORDER BY TaxRate ASC) AS FirstValue
 FROM SalesTaxRate;


In this example, the FIRST_VALUE function is used to return the ID of the state or province with the
lowest tax rate. The OVER clause is used to order the tax rates to obtain the lowest rate.

 StateProvinceID       Name                              TaxRate     FirstValue

 74                    Utah State Sales Tax              5.00        74

 36                    Minnesota State Sales Tax         6.75        74

 30                    Massachusetts State Sales Tax     7.00        74



 StateProvinceID       Name                             TaxRate    FirstValue

 1                     Canadian GST                     7.00       74

 57                    Canadian GST                     7.00       74

 63                    Canadian GST                     7.00       74

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
