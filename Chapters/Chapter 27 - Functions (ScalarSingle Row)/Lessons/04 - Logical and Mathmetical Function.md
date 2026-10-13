---
lesson_id: C27-L04
chapter: 27
lesson: 4
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C27-L04: Logical and Mathmetical Function

## Textbook excerpt

Logical and Mathmetical Function

SQL has two logical functions – CHOOSE and IIF.
The CHOOSE function returns an item from a list of values, based on its position in the list. This
position is specified by the index.

In the syntax, the index parameter specifies the item and is a whole number, or integer. The val_1
… val_n parameter identifies the list of values.

 SELECT CHOOSE(2, 'Human Resources', 'Sales', 'Admin', 'Marketing' ) AS Result;



 Result

 Sales

In this example, you use the CHOOSE function to return the second entry in a list of departments.


The IIF function returns one of two values, based on a particular condition. If the condition is true,
it will return true value. Otherwise it will return a false value.

In the syntax, the boolean_expression parameter specifies the Boolean expression. The
true_value parameter specifies the value that should be returned if the boolean_expression
evaluates to true and the false_value parameter specifies the value that should be returned if the
boolean_expression evaluates to false.

 SELECT BusinessEntityID, SalesYTD,
        IIF(SalesYTD > 200000, 'Bonus', 'No Bonus') AS 'Bonus?'
 FROM Sales.SalesPerson
 GO



 BusinessEntityID          SalesYTD       Bonus?

 274                       559697.5639    Bonus

 275                       3763178.1787   Bonus

 285                       172524.4512    No Bonus


In this example, you use the IIF function to return one of two values. If a sales person's year-to-
date sales are above 200,000, this person will be eligible for a bonus. Values below 200,000 mean
that employees don't qualify for bonuses.



SQL includes several mathematical functions that you can
use to perform calculations on input values and return
numeric results.

One example is the SIGN function, which returns a value indicating the sign of an expression. The
value of -1 indicates a negative expression, the value of +1 indicates a positive expression, and 0
indicates zero.

 SELECT SIGN(-20) AS 'Sign'



 Sign

 -1

In the example, the input is a negative number, so the Results pane lists the result -1.


Another mathematical function is the POWER function. This function provides the value of an
expression raised to a specified power.

In the syntax, the float_expression parameter specifies the expression, and the y parameter
specifies the power to which you want to raise the expression.

 SELECT POWER(50, 3) AS Result



 Result

 125000

Read Functions (Scalar/Single Row) online: https://riptutorial.com/sql/topic/6898/functions--scalar-
single-row-

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
