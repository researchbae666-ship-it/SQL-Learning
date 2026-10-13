---
lesson_id: C27-L01
chapter: 27
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C27-L01: Character modifications

## Textbook excerpt

Chapter 27: Functions (Scalar/Single Row)
Introduction
SQL provides several built-in scalar functions. Each scalar function takes one value as input and
returns one value as output for each row in a result set.

You use scalar functions wherever an expression is allowed within a T-SQL statement.


Syntax
   • CAST ( expression AS data_type [ ( length ) ] )
   • CONVERT ( data_type [ ( length ) ] , expression [ , style ] )
   • PARSE ( string_value AS data_type [ USING culture ] )
   • DATENAME ( datepart , date )
   • GETDATE ( )
   • DATEDIFF ( datepart , startdate , enddate )
   • DATEADD (datepart , number , date )
   • CHOOSE ( index, val_1, val_2 [, val_n ] )
   • IIF ( boolean_expression, true_value, false_value )
   • SIGN ( numeric_expression )
   • POWER ( float_expression , y )


Remarks
Scalar or Single-Row functions are used to operate each row of data in the result set, as opposed
to aggregate functions which operate on the entire result set.

There are ten types of scalar functions.

   1. Configuration functions provide information about the configuration of the current SQL
      instance.
   2. Conversion functions convert data into the correct data type for a given operation. For
      example, these types of functions can reformat information by converting a string to a date or
      number to allow two different types to be compared.
   3. Date and time functions manipulate fields containing date and time values. They can return
      numeric, date, or string values. For example, you can use a function to retrieve the current
      day of the week or year or to retrieve only the year from the date.

The values returned by date and time functions depend on the date and time set for the operating
system of the computer running the SQL instance.

   4. Logical function that performs operations using logical operators. It evaluates a set of
      conditions and returns a single result.
   5. Mathematical functions perform mathematical operations, or calculations, on numeric



      expressions. This type of function returns a single numeric value.
   6. Metadata functions retrieve information about a specified database, such as its name and
      database objects.
   7. Security functions provide information that you can use to manage the security of a
      database, such as information about database users and roles.
   8. String functions perform operations on string values and return either numeric or string
      values.

Using string functions, you can, for example, combine data, extract a substring, compare strings,
or convert a string to all uppercase or lowercase characters.

   9. System functions perform operations and return information about values, objects, and
      settings for the current SQL instance
  10. System statistical functions provide various statistics about the current SQL instance – for
      example, so that you can monitor the system's current performance levels.


Examples
Character modifications

Character modifying functions include converting characters to upper or lower case characters,
converting numbers to formatted numbers, performing character manipulation, etc.

The lower(char) function converts the given character parameter to be lower-cased characters.

 SELECT customer_id, lower(customer_last_name) FROM customer;


would return the customer's last name changed from "SMITH" to "smith".

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
