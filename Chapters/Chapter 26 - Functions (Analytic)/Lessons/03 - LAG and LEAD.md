---
lesson_id: C26-L03
chapter: 26
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C26-L03: LAG and LEAD

## Textbook excerpt

LAG and LEAD

The LAG function provides data on rows before the current row in the same result set. For example,
in a SELECT statement, you can compare values in the current row with values in a previous row.

You use a scalar expression to specify the values that should be compared. The offset parameter
is the number of rows before the current row that will be used in the comparison. If you don't
specify the number of rows, the default value of one row is used.

The default parameter specifies the value that should be returned when the expression at offset
has a NULL value. If you don't specify a value, a value of NULL is returned.


The LEAD function provides data on rows after the current row in the row set. For example, in a



SELECT statement, you can compare values in the current row with values in the following row.


You specify the values that should be compared using a scalar expression. The offset parameter
is the number of rows after the current row that will be used in the comparison.

You specify the value that should be returned when the expression at offset has a NULL value using
the default parameter. If you don't specify these parameters, the default of one row is used and a
value of NULL is returned.

 SELECT BusinessEntityID, SalesYTD,
        LEAD(SalesYTD, 1, 0) OVER(ORDER BY BusinessEntityID) AS "Lead value",
        LAG(SalesYTD, 1, 0) OVER(ORDER BY BusinessEntityID) AS "Lag value"
 FROM SalesPerson;


This example uses the LEAD and LAG functions to compare the sales values for each employee
to date with those of the employees listed above and below, with records ordered based on the
BusinessEntityID column.

 BusinessEntityID          SalesYTD       Lead value     Lag value

 274                       559697.5639    3763178.1787   0.0000

 275                       3763178.1787   4251368.5497   559697.5639

 276                       4251368.5497   3189418.3662   3763178.1787

 277                       3189418.3662   1453719.4653   4251368.5497

 278                       1453719.4653   2315185.6110   3189418.3662

 279                       2315185.6110   1352577.1325   1453719.4653

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
