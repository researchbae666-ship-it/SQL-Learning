---
lesson_id: C05-L01
chapter: 5
lesson: 1
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C05-L01: Searched CASE in SELECT (Matches a boolean expression)

**Chapter:** 5 · **Lesson:** 1 of 6 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Chapter 5: CASE
Introduction
The CASE expression is used to implement if-then logic.


Syntax
      • CASE input_expression
         WHEN compare1 THEN result1
        [WHEN compare2 THEN result2]...
        [ELSE resultX]
        END
      • CASE
         WHEN condition1 THEN result1
        [WHEN condition2 THEN result2]...
        [ELSE resultX]
        END


Remarks
The simple CASE expression returns the first result whose compareX value is equal to the
input_expression.


The searched CASE expression returns the first result whose conditionX is true.


Examples
Searched CASE in SELECT (Matches a boolean expression)

The searched CASE returns results when a boolean expression is TRUE.

(This differs from the simple case, which can only check for equivalency with an input.)

 SELECT Id, ItemId, Price,
   CASE WHEN Price < 10 THEN 'CHEAP'
        WHEN Price < 20 THEN 'AFFORDABLE'
        ELSE 'EXPENSIVE'
   END AS PriceRating
 FROM ItemSales



 Id     ItemId   Price     PriceRating

 1      100      34.5      EXPENSIVE

 2      145      2.3       CHEAP


 Id   ItemId    Price      PriceRating

 3    100       34.5       EXPENSIVE

 4    100       34.5       EXPENSIVE

 5    145       10         AFFORDABLE


Use CASE to COUNT the number of rows in a column match a condition.

Use Case

CASE can be used in conjunction with SUM to return a count of only those items matching a pre-
defined condition. (This is similar to COUNTIF in Excel.)

The trick is to return binary results indicating matches, so the "1"s returned for matching entries
can be summed for a count of the total number of matches.

Given this table ItemSales, let's say you want to learn the total number of items that have been
categorized as "Expensive":

 Id   ItemId    Price      PriceRating

 1    100       34.5       EXPENSIVE

 2    145       2.3        CHEAP

 3    100       34.5       EXPENSIVE

 4    100       34.5       EXPENSIVE

 5    145       10         AFFORDABLE

Query

 SELECT
     COUNT(Id) AS ItemsCount,
     SUM ( CASE
             WHEN PriceRating = 'Expensive' THEN 1
             ELSE 0
           END
         ) AS ExpensiveItemsCount
 FROM ItemSales


Results:

 ItemsCount      ExpensiveItemsCount

 5               3




Alternative:

 SELECT
     COUNT(Id) as ItemsCount,
     SUM (
         CASE PriceRating
             WHEN 'Expensive' THEN 1
             ELSE 0
         END
        ) AS ExpensiveItemsCount
 FROM ItemSales

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
