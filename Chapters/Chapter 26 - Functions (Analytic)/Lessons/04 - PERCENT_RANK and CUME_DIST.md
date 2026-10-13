---
lesson_id: C26-L04
chapter: 26
lesson: 4
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C26-L04: PERCENT_RANK and CUME_DIST

## Textbook excerpt

PERCENT_RANK and CUME_DIST

The PERCENT_RANK function calculates the ranking of a row relative to the row set. The percentage is
based on the number of rows in the group that have a lower value than the current row.

The first value in the result set always has a percent rank of zero. The value for the highest-ranked
– or last – value in the set is always one.


The CUME_DIST function calculates the relative position of a specified value in a group of values, by
determining the percentage of values less than or equal to that value. This is called the cumulative
distribution.

 SELECT BusinessEntityID, JobTitle, SickLeaveHours,
 PERCENT_RANK() OVER(PARTITION BY JobTitle ORDER BY SickLeaveHours DESC)
        AS "Percent Rank",
 CUME_DIST() OVER(PARTITION BY JobTitle ORDER BY SickLeaveHours DESC)
        AS "Cumulative Distribution"




 FROM Employee;


In this example, you use an ORDER clause to partition – or group – the rows retrieved by the SELECT
statement based on employees' job titles, with the results in each group sorted based on the
numbers of sick leave hours that employees have used.

                                                                                   Cumulative
 BusinessEntityID          JobTitle      SickLeaveHours   Percent Rank
                                                                                   Distribution

                           Application
 267                                     57               0                        0.25
                           Specialist

                           Application
 268                                     56               0.333333333333333        0.75
                           Specialist

                           Application
 269                                     56               0.333333333333333        0.75
                           Specialist

                           Application
 272                                     55               1                        1
                           Specialist

                           Assitant to
                           the Cheif
 262                                     48               0                        1
                           Financial
                           Officer

                           Benefits
 239                                     45               0                        1
                           Specialist

 252                       Buyer         50               0                        0.111111111111111

 251                       Buyer         49               0.125                    0.333333333333333

 256                       Buyer         49               0.125                    0.333333333333333

 253                       Buyer         48               0.375                    0.555555555555555

 254                       Buyer         48               0.375                    0.555555555555555

The PERCENT_RANK function ranks the entries within each group. For each entry, it returns the
percentage of entries in the same group that have lower values.

The CUME_DIST function is similar, except that it returns the percentage of values less than or equal
to the current value.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
