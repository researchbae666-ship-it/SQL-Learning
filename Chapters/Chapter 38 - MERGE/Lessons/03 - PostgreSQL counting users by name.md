---
lesson_id: C38-L03
chapter: 38
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C38-L03: PostgreSQL: counting users by name

## Textbook excerpt

PostgreSQL: counting users by name

Suppose we want to know how many users have the same name. Let us create table users as
follows:

 create table users(
     id serial,
     name varchar(8) unique,
     count int
 );


Now, we just discovered a new user named Joe and would like to take him into account. To
achieve that, we need to determine whether there is an existing row with his name, and if so,
update it to increment count; on the other hand, if there is no existing row, we should create it.

PostgreSQL uses the following syntax : insert … on conflict … do update …. In this case:

 insert into users(name, count)
     values('Joe', 1)
     on conflict (name) do update set count = users.count + 1;


Read MERGE online: https://riptutorial.com/sql/topic/1470/merge

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
