---
lesson_id: C06-L04
chapter: 6
lesson: 4
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C06-L04: Joins

**Chapter:** 6 · **Lesson:** 4 of 4 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Joins

Explicit joins should always be used; implicit joins have several problems:

   • The join condition is somewhere in the WHERE clause, mixed up with any other filter
     conditions. This makes it harder to see which tables are joined, and how.

   • Due to the above, there is a higher risk of mistakes, and it is more likely that they are found
     later.

   • In standard SQL, explicit joins are the only way to use outer joins:

       SELECT d.Name,
              e.Fname || e.LName AS EmpName
       FROM      Departments AS d
       LEFT JOIN Employees   AS e ON d.ID = e.DepartmentID;


   • Explicit joins allow using the USING clause:

       SELECT RecipeID,




              Recipes.Name,
              COUNT(*) AS NumberOfIngredients
       FROM      Recipes
       LEFT JOIN Ingredients USING (RecipeID);


      (This requires that both tables use the same column name.
      USING automatically removes the duplicate column from the result, e.g., the join in this
      query returns a single RecipeID column.)

Read Clean Code in SQL online: https://riptutorial.com/sql/topic/9843/clean-code-in-sql

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
