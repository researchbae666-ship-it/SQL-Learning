---
lesson_id: C29-L01
chapter: 29
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C29-L01: USE GROUP BY to COUNT the number of rows for each unique entry in a given column

## Textbook excerpt

Chapter 29: GROUP BY
Introduction
Results of a SELECT query can be grouped by one or more columns using the GROUP BY
statement: all results with the same value in the grouped columns are aggregated together. This
generates a table of partial results, instead of one result. GROUP BY can be used in conjunction
with aggregation functions using the HAVING statement to define how non-grouped columns are
aggregated.


Syntax
   • GROUP BY {
           column-expression
         | ROLLUP ( <group_by_expression> [ ,...n ] )
         | CUBE ( <group_by_expression> [ ,...n ] )
         | GROUPING SETS ( [ ,...n ] )
         | () --calculates the grand total
     } [ ,...n ]

   • <group_by_expression> ::=
         column-expression
       | ( column-expression [ ,...n ] )

   • <grouping_set> ::=
         () --calculates the grand total
       | <grouping_set_item>
       | ( <grouping_set_item> [ ,...n ] )

   • <grouping_set_item> ::=
         <group_by_expression>
       | ROLLUP ( <group_by_expression> [ ,...n ] )
       | CUBE ( <group_by_expression> [ ,...n ] )


Examples
USE GROUP BY to COUNT the number of rows for each unique entry in a
given column

Let's say you want to generate counts or subtotals for a given value in a column.

Given this table, "Westerosians":





 Name        GreatHouseAllegience

 Arya        Stark

 Cercei      Lannister

 Myrcella    Lannister

 Yara        Greyjoy

 Catelyn     Stark

 Sansa       Stark

Without GROUP BY, COUNT will simply return a total number of rows:

 SELECT Count(*) Number_of_Westerosians
 FROM Westerosians


returns...

 Number_of_Westerosians

 6

But by adding GROUP BY, we can COUNT the users for each value in a given column, to return
the number of people in a given Great House, say:

 SELECT GreatHouseAllegience House, Count(*) Number_of_Westerosians
 FROM Westerosians
 GROUP BY GreatHouseAllegience


returns...

 House        Number_of_Westerosians

 Stark        3

 Greyjoy      1

 Lannister    2

It's common to combine GROUP BY with ORDER BY to sort results by largest or smallest
category:

 SELECT GreatHouseAllegience House, Count(*) Number_of_Westerosians
 FROM Westerosians
 GROUP BY GreatHouseAllegience
 ORDER BY Number_of_Westerosians Desc





returns...

 House        Number_of_Westerosians

 Stark        3

 Lannister    2

 Greyjoy      1

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
