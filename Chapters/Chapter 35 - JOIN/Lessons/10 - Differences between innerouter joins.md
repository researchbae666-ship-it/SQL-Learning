---
lesson_id: C35-L10
chapter: 35
lesson: 10
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C35-L10: Differences between inner/outer joins

## Textbook excerpt

Differences between inner/outer joins

SQL has various join types to specify whether (non-)matching rows are included in the result:
INNER JOIN, LEFT OUTER JOIN, RIGHT OUTER JOIN, and FULL OUTER JOIN (the INNER and OUTER keywords
are optional). The figure below underlines the differences between these types of joins: the blue
area represents the results returned by the join, and the white area represents the results that the
join will not return.






here.



Right Anti Semi Join
Includes right rows that do not match left rows.




 SELECT * FROM B WHERE Y NOT IN (SELECT X FROM A);

 Y
 -------
 Tim
 Vincent


As you can see, there is no dedicated NOT IN syntax for left vs. right anti semi join - we achieve
the effect simply by switching the table positions within SQL text.



Cross Join
A Cartesian product of all left with all right rows.

 SELECT * FROM A CROSS JOIN B;

 X       Y
 -----   -------
 Amy     Lisa




 John     Lisa
 Lisa     Lisa
 Marco    Lisa
 Phil     Lisa
 Amy      Marco
 John     Marco
 Lisa     Marco
 Marco    Marco
 Phil     Marco
 Amy      Phil
 John     Phil
 Lisa     Phil
 Marco    Phil
 Phil     Phil
 Amy      Tim
 John     Tim
 Lisa     Tim
 Marco    Tim
 Phil     Tim
 Amy      Vincent
 John     Vincent
 Lisa     Vincent
 Marco    Vincent
 Phil     Vincent


Cross join is equivalent to an inner join with join condition which always matches, so the following
query would have returned the same result:

 SELECT * FROM A JOIN B ON 1 = 1;




Self-Join
This simply denotes a table joining with itself. A self-join can be any of the join types discussed
above. For example, this is a an inner self-join:

 SELECT * FROM A A1 JOIN A A2 ON LEN(A1.X) < LEN(A2.X);

 X       X
 ----    -----
 Amy     John
 Amy     Lisa
 Amy     Marco
 John    Marco
 Lisa    Marco
 Phil    Marco
 Amy     Phil


Read JOIN online: https://riptutorial.com/sql/topic/261/join

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
