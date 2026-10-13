---
lesson_id: C35-L08
chapter: 35
lesson: 8
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C35-L08: FULL JOIN

## Textbook excerpt

FULL JOIN

One type of JOIN that is less known, is the FULL JOIN.
(Note: FULL JOIN is not supported by MySQL as per 2016)

A FULL OUTER JOIN returns all rows from the left table, and all rows from the right table.

If there are rows in the left table that do not have matches in the right table, or if there are rows in
right table that do not have matches in the left table, then those rows will be listed, too.

Example 1 :

 SELECT * FROM Table1

 FULL JOIN Table2
      ON 1 = 2


Example 2:

 SELECT
      COALESCE(T_Budget.Year, tYear.Year) AS RPT_BudgetInYear
     ,COALESCE(T_Budget.Value, 0.0) AS RPT_Value
 FROM T_Budget

 FULL JOIN tfu_RPT_All_CreateYearInterval(@budget_year_from, @budget_year_to) AS tYear
       ON tYear.Year = T_Budget.Year


Note that if you're using soft-deletes, you'll have to check the soft-delete status again in the
WHERE-clause (because FULL JOIN behaves kind-of like a UNION);
It's easy to overlook this little fact, since you put AP_SoftDeleteStatus = 1 in the join clause.

Also, if you are doing a FULL JOIN, you'll usually have to allow NULL in the WHERE-clause;
forgetting to allow NULL on a value will have the same effects as an INNER join, which is
something you don't want if you're doing a FULL JOIN.

Example:




 SELECT
      T_AccountPlan.AP_UID
     ,T_AccountPlan.AP_Code
     ,T_AccountPlan.AP_Lang_EN
     ,T_BudgetPositions.BUP_Budget
     ,T_BudgetPositions.BUP_UID
     ,T_BudgetPositions.BUP_Jahr
 FROM T_BudgetPositions

 FULL JOIN T_AccountPlan
     ON T_AccountPlan.AP_UID = T_BudgetPositions.BUP_AP_UID
     AND T_AccountPlan.AP_SoftDeleteStatus = 1

 WHERE (1=1)
 AND (T_BudgetPositions.BUP_SoftDeleteStatus = 1 OR T_BudgetPositions.BUP_SoftDeleteStatus IS
 NULL)
 AND (T_AccountPlan.AP_SoftDeleteStatus = 1 OR T_AccountPlan.AP_SoftDeleteStatus IS NULL)

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
