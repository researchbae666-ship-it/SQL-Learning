---
lesson_id: C53-L03
chapter: 53
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C53-L03: Subquery in SELECT clause

## Textbook excerpt

Subquery in SELECT clause

 SELECT
   Id,
   FName,
   LName,
   (SELECT COUNT(*) FROM Cars WHERE Cars.CustomerId = Customers.Id) AS NumberOfCars
 FROM Customers



Subqueries in FROM clause

You can use subqueries to define a temporary table and use it in the FROM clause of an "outer"
query.



    SELECT * FROM (SELECT city, temp_hi - temp_lo AS temp_var FROM weather) AS w
    WHERE temp_var > 20;


The above finds cities from the weather table whose daily temperature variation is greater than 20.
The result is:

    city              temp_var

    ST LOUIS          21

    LOS ANGELES       31

    LOS ANGELES       23

    LOS ANGELES       31

    LOS ANGELES       27

    LOS ANGELES       28

    LOS ANGELES       28

    LOS ANGELES       32

.

Subqueries in WHERE clause

The following example finds cities (from the cities example) whose population is below the
average temperature (obtained via a sub-qquery):

    SELECT name, pop2000 FROM cities
    WHERE pop2000 < (SELECT avg(pop2000)   FROM cities);


Here: the subquery (SELECT avg(pop2000) FROM cities) is used to specify conditions in the
WHERE clause. The result is:

    name            pop2000

    San Francisco   776733

    ST LOUIS        348189

    Kansas City     146866


Subqueries in SELECT clause

Subqueries can also be used in the SELECT part of the outer query. The following query shows all



weather table columns with the corresponding states from the cities table.

 SELECT w.*, (SELECT c.state FROM cities AS c WHERE c.name = w.city ) AS state
 FROM weather AS w;

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
