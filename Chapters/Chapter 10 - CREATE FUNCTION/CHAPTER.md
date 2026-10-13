# Chapter 10: CREATE FUNCTION

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 10: CREATE FUNCTION
Syntax
   • CREATE FUNCTION function_name ( [list_of_paramenters] ) RETURNS return_data_type
     AS BEGIN function_body RETURN scalar_expression END


Parameters

 Argument                  Description

 function_name             the name of function

 list_of_paramenters       parameters that function accepts

 return_data_type          type that function returs. Some SQL data type

 function_body             the code of function

 scalar_expression         scalar value returned by function


Remarks
CREATE FUNCTION creates a user-defined function that can be used when doing a SELECT,
INSERT, UPDATE, or DELETE query. The functions can be created to return a single variable or
a single table.


Examples
Create a new Function

 CREATE FUNCTION FirstWord (@input varchar(1000))
 RETURNS varchar(1000)
 AS
 BEGIN
     DECLARE @output varchar(1000)
     SET @output = SUBSTRING(@input, 0, CASE CHARINDEX(' ', @input)
          WHEN 0 THEN LEN(@input) + 1
          ELSE CHARINDEX(' ', @input)
     END)

       RETURN @output
 END


This example creates a function named FirstWord, that accepts a varchar parameter and returns
another varchar value.



Read CREATE FUNCTION online: https://riptutorial.com/sql/topic/2437/create-function
