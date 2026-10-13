---
lesson_id: C27-L03
chapter: 27
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C27-L03: Configuration and Conversion Function

## Textbook excerpt

Configuration and Conversion Function

An example of a configuration function in SQL is the @@SERVERNAME function. This function provides
the name of the local server that's running SQL.

 SELECT @@SERVERNAME AS 'Server'



 Server

 SQL064


In SQL, most data conversions occur implicitly, without any user intervention.

To perform any conversions that can't be completed implicitly, you can use the CAST or CONVERT
functions.

The CAST function syntax is simpler than the CONVERT function syntax, but is limited in what it can do.

In here, we use both the CAST and CONVERT functions to convert the datetime data type to the varchar
data type.

The CAST function always uses the default style setting. For example, it will represent dates and
times using the format YYYY-MM-DD.

The CONVERT function uses the date and time style you specify. In this case, 3 specifies the date
format dd/mm/yy.

 USE AdventureWorks2012
 GO
 SELECT FirstName + ' ' + LastName + ' was hired on ' +
        CAST(HireDate AS varchar(20)) AS 'Cast',
        FirstName + ' ' + LastName + ' was hired on ' +
        CONVERT(varchar, HireDate, 3) AS 'Convert'
 FROM Person.Person AS p
 JOIN HumanResources.Employee AS e
 ON p.BusinessEntityID = e.BusinessEntityID
 GO



 Cast                                          Convert

 David Hamiltion was hired on 2003-02-04       David Hamiltion was hired on 04/02/03


Another example of a conversion function is the PARSE function. This function converts a string to a
specified data type.

In the syntax for the function, you specify the string that must be converted, the AS keyword, and
then the required data type. Optionally, you can also specify the culture in which the string value
should be formatted. If you don't specify this, the language for the session is used.




If the string value can't be converted to a numeric, date, or time format, it will result in an error.
You'll then need to use CAST or CONVERT for the conversion.

 SELECT PARSE('Monday, 13 August 2012' AS datetime2 USING 'en-US') AS 'Date in English'



 Date in English

 2012-08-13 00:00:00.0000000

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
