---
lesson_id: C36-L07
chapter: 36
lesson: 7
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C36-L07: Wildcard characters

## Textbook excerpt

Wildcard characters

wildcard characters are used with the SQL LIKE operator. SQL wildcards are used to search for
data within a table.

Wildcards in SQL are:%, _, [charlist], [^charlist]

% - A substitute for zero or more characters

       Eg:   //selects all customers with a City starting with "Lo"
             SELECT * FROM Customers
             WHERE City LIKE 'Lo%';





         //selects all customers with a City containing the pattern "es"
        SELECT * FROM Customers
         WHERE City LIKE '%es%';


_ - A substitute for a single character

 Eg://selects all customers with a City starting with any character, followed by "erlin"
 SELECT * FROM Customers
 WHERE City LIKE '_erlin';


[charlist] - Sets and ranges of characters to match

 Eg://selects all customers with a City starting with "a", "d", or "l"
 SELECT * FROM Customers
 WHERE City LIKE '[adl]%';

 //selects all customers with a City starting with "a", "d", or "l"
 SELECT * FROM Customers
 WHERE City LIKE '[a-c]%';


[^charlist] - Matches only a character NOT specified within the brackets

 Eg://selects all customers with a City starting with a character that is not "a", "p", or "l"
 SELECT * FROM Customers
 WHERE City LIKE '[^apl]%';

 or

 SELECT * FROM Customers
 WHERE City NOT LIKE '[apl]%' and city like '_%';


Read LIKE operator online: https://riptutorial.com/sql/topic/860/like-operator

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
