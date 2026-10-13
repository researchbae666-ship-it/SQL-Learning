---
lesson_id: C63-L02
chapter: 63
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C63-L02: Setting up a flag if other rows have a common property

## Textbook excerpt

Setting up a flag if other rows have a common property

Let's say I have this data:

Table items

 id   name         tag

 1    example      unique_tag

 2    foo          simple

 42   bar          simple

 3    baz          hello

 51   quux         world

I'd like to get all those lines and know if a tag is used by other lines

 SELECT id, name, tag, COUNT(*) OVER (PARTITION BY tag) > 1 AS flag FROM items





The result will be:

 id     name       tag             flag

 1      example    unique_tag      false

 2      foo        simple          true

 42     bar        simple          true

 3      baz        hello           false

 51     quux       world           false

In case your database doesn't have OVER and PARTITION you can use this to produce the same
result:

 SELECT id, name, tag, (SELECT COUNT(tag) FROM items B WHERE tag = A.tag) > 1 AS flag FROM
 items A

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
