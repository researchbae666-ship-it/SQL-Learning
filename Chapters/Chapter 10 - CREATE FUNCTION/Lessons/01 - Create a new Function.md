---
lesson_id: C10-L01
chapter: 10
lesson: 1
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C10-L01: Create a new Function

**Chapter:** 10 · **Lesson:** 1 of 1 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

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

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
