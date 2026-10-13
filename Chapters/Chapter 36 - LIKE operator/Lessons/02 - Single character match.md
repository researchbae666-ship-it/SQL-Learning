---
lesson_id: C36-L02
chapter: 36
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C36-L02: Single character match

## Textbook excerpt

Single character match

To broaden the selections of a structured query language (SQL-SELECT) statement, wildcard
characters, the percent sign (%) and the underscore (_), can be used.

The _ (underscore) character can be used as a wildcard for any single character in a pattern
match.

Find all employees whose Fname start with 'j' and end with 'n' and has exactly 3 characters in
Fname.

 SELECT * FROM Employees WHERE FName LIKE 'j_n'


_ (underscore) character can also be used more than once as a wild card to match patterns.


For example, this pattern would match "jon", "jan", "jen", etc.

These names will not be shown "jn","john","jordan", "justin", "jason", "julian", "jillian", "joann"
because in our query one underscore is used and it can skip exactly one character, so result must
be of 3 character Fname.

For example, this pattern would match "LaSt", "LoSt", "HaLt", etc.

 SELECT * FROM Employees WHERE FName LIKE '_A_T'

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
