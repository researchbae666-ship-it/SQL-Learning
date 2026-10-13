---
lesson_id: C45-L20
chapter: 45
lesson: 20
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C45-L20: Selecting with more than 1 condition.

## Textbook excerpt

Selecting with more than 1 condition.

The AND keyword is used to add more conditions to the query.

 Name     Age       Gender

 Sam      18        M

 John     21        M

 Bob      22        M

 Mary     23        F

 SELECT name FROM persons WHERE gender = 'M' AND age > 20;


This will return:

 Name

 John

 Bob


using OR keyword

 SELECT name FROM persons WHERE gender = 'M' OR age < 20;


This will return:

 name

 Sam

 John

 Bob

These keywords can be combined to allow for more complex criteria combinations:

 SELECT name
 FROM persons
 WHERE (gender = 'M' AND age < 20)
    OR (gender = 'F' AND age > 20);


This will return:

 name

 Sam

 Mary

Read SELECT online: https://riptutorial.com/sql/topic/222/select

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
