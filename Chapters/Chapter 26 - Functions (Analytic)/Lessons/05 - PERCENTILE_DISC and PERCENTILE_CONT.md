---
lesson_id: C26-L05
chapter: 26
lesson: 5
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C26-L05: PERCENTILE_DISC and PERCENTILE_CONT

## Textbook excerpt

PERCENTILE_DISC and PERCENTILE_CONT

The PERCENTILE_DISC function lists the value of the first entry where the cumulative distribution is



higher than the percentile that you provide using the numeric_literal parameter.

The values are grouped by rowset or partition, as specified by the WITHIN GROUP clause.


The PERCENTILE_CONT function is similar to the PERCENTILE_DISC function, but returns the average of
the sum of the first matching entry and the next entry.

 SELECT BusinessEntityID, JobTitle, SickLeaveHours,
        CUME_DIST() OVER(PARTITION BY JobTitle ORDER BY SickLeaveHours ASC)
        AS "Cumulative Distribution",
        PERCENTILE_DISC(0.5) WITHIN GROUP(ORDER BY SickLeaveHours)
           OVER(PARTITION BY JobTitle) AS "Percentile Discreet"
 FROM Employee;


To find the exact value from the row that matches or exceeds the 0.5 percentile, you pass the
percentile as the numeric literal in the PERCENTILE_DISC function. The Percentile Discreet column in
a result set lists the value of the row at which the cumulative distribution is higher than the
specified percentile.

                                                              Cumulative           Percentile
 BusinessEntityID          JobTitle      SickLeaveHours
                                                              Distribution         Discreet

                           Application
 272                                     55                   0.25                 56
                           Specialist

                           Application
 268                                     56                   0.75                 56
                           Specialist

                           Application
 269                                     56                   0.75                 56
                           Specialist

                           Application
 267                                     57                   1                    56
                           Specialist


To base the calculation on a set of values, you use the PERCENTILE_CONT function. The "Percentile
Continuous" column in the results lists the average value of the sum of the result value and the
next highest matching value.

 SELECT BusinessEntityID, JobTitle, SickLeaveHours,
        CUME_DIST() OVER(PARTITION BY JobTitle ORDER BY SickLeaveHours ASC)
        AS "Cumulative Distribution",
        PERCENTILE_DISC(0.5) WITHIN GROUP(ORDER BY SickLeaveHours)
           OVER(PARTITION BY JobTitle) AS "Percentile Discreet",
        PERCENTILE_CONT(0.5) WITHIN GROUP(ORDER BY SickLeaveHours)
           OVER(PARTITION BY JobTitle) AS "Percentile Continuous"
 FROM Employee;





                                                          Cumulative      Percentile   Percentile
 BusinessEntityID          JobTitle      SickLeaveHours
                                                          Distribution    Discreet     Continuous

                           Application
 272                                     55               0.25            56           56
                           Specialist

                           Application
 268                                     56               0.75            56           56
                           Specialist

                           Application
 269                                     56               0.75            56           56
                           Specialist

                           Application
 267                                     57               1               56           56
                           Specialist

Read Functions (Analytic) online: https://riptutorial.com/sql/topic/8811/functions--analytic-

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
