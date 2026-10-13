---
lesson_id: C63-L05
chapter: 63
lesson: 5
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C63-L05: Finding "out-of-sequence" records using the LAG() function

## Textbook excerpt

Finding "out-of-sequence" records using the LAG() function

Given these sample data:

 ID     STATUS     STATUS_TIME                   STATUS_BY

 1      ONE        2016-09-28-19.47.52.501398    USER_1

 3      ONE        2016-09-28-19.47.52.501511    USER_2

 1      THREE      2016-09-28-19.47.52.501517    USER_3




 ID   STATUS       STATUS_TIME                    STATUS_BY

 3    TWO          2016-09-28-19.47.52.501521     USER_2

 3    THREE        2016-09-28-19.47.52.501524     USER_4

Items identified by ID values must move from STATUS 'ONE' to 'TWO' to 'THREE' in sequence,
without skipping statuses. The problem is to find users (STATUS_BY) values who violate the rule and
move from 'ONE' immediately to 'THREE'.

The LAG() analytical function helps to solve the problem by returning for each row the value in the
preceding row:

 SELECT * FROM (
  SELECT
   t.*,
   LAG(status) OVER (PARTITION BY id ORDER BY status_time) AS prev_status
   FROM test t
 ) t1 WHERE status = 'THREE' AND prev_status != 'TWO'


In case your database doesn't have LAG() you can use this to produce the same result:

 SELECT A.id, A.status, B.status as prev_status, A.status_time, B.status_time as
 prev_status_time
 FROM Data A, Data B
 WHERE A.id = B.id
 AND   B.status_time = (SELECT MAX(status_time) FROM Data where status_time < A.status_time and
 id = A.id)
 AND   A.status = 'THREE' AND NOT B.status = 'TWO'


Read Window Functions online: https://riptutorial.com/sql/topic/647/window-functions

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
