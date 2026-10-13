---
lesson_id: C25-L03
chapter: 25
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C25-L03: AVG()

## Textbook excerpt

AVG()

The aggregate function AVG() returns the average of a given expression, usually numeric values
in a column. Assume we have a table containing the yearly calculation of population in cities
across the world. The records for New York City look similar to the ones below:


EXAMPLE TABLE

 city_name         population      year

 New York City     8,550,405       2015

 New York City     ...             ...

 New York City     8,000,906       2005

To select the average population of the New York City, USA from a table containing city names,
population measurements, and measurement years for last ten years:


QUERY

 select city_name, AVG(population) avg_population
 from city_population
 where city_name = 'NEW YORK CITY';


Notice how measurement year is absent from the query since population is being averaged over
time.



RESULTS

 city_name         avg_population

 New York City     8,250,754

      Note: The AVG() function will convert values to numeric types. This is especially
      important to keep in mind when working with dates.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
