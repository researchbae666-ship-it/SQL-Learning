---
lesson_id: C08-L04
chapter: 8
lesson: 4
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C08-L04: Oracle CONNECT BY functionality with recursive CTEs

**Chapter:** 8 · **Lesson:** 4 of 6 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Oracle CONNECT BY functionality with recursive CTEs

Oracle's CONNECT BY functionality provides many useful and nontrivial features that are not
built-in when using SQL standard recursive CTEs. This example replicates these features (with a
few additions for sake of completeness), using SQL Server syntax. It is most useful for Oracle
developers finding many features missing in their hierarchical queries on other databases, but it
also serves to showcase what can be done with a hierarchical query in general.

   WITH tbl AS (
        SELECT id, name, parent_id
          FROM mytable)
      , tbl_hierarchy AS (
        /* Anchor */
        SELECT 1 AS "LEVEL"
             --, 1 AS CONNECT_BY_ISROOT
             --, 0 AS CONNECT_BY_ISBRANCH
             , CASE WHEN t.id IN (SELECT parent_id FROM tbl) THEN 0 ELSE 1 END AS
 CONNECT_BY_ISLEAF
             , 0 AS CONNECT_BY_ISCYCLE
             , '/' + CAST(t.id   AS VARCHAR(MAX)) + '/' AS SYS_CONNECT_BY_PATH_id
             , '/' + CAST(t.name AS VARCHAR(MAX)) + '/' AS SYS_CONNECT_BY_PATH_name
             , t.id AS root_id
             , t.*
          FROM tbl t
         WHERE t.parent_id IS NULL                            -- START WITH parent_id IS NULL
        UNION ALL
        /* Recursive */
        SELECT th."LEVEL" + 1 AS "LEVEL"
             --, 0 AS CONNECT_BY_ISROOT
             --, CASE WHEN t.id IN (SELECT parent_id FROM tbl) THEN 1 ELSE 0 END AS
 CONNECT_BY_ISBRANCH
             , CASE WHEN t.id IN (SELECT parent_id FROM tbl) THEN 0 ELSE 1 END AS
 CONNECT_BY_ISLEAF
             , CASE WHEN th.SYS_CONNECT_BY_PATH_id LIKE '%/' + CAST(t.id AS VARCHAR(MAX)) +
 '/%' THEN 1 ELSE 0 END AS CONNECT_BY_ISCYCLE
             , th.SYS_CONNECT_BY_PATH_id   + CAST(t.id   AS VARCHAR(MAX)) + '/' AS
 SYS_CONNECT_BY_PATH_id
             , th.SYS_CONNECT_BY_PATH_name + CAST(t.name AS VARCHAR(MAX)) + '/' AS
 SYS_CONNECT_BY_PATH_name
             , th.root_id
             , t.*
          FROM tbl t




               JOIN tbl_hierarchy th ON (th.id = t.parent_id) -- CONNECT BY PRIOR id =
 parent_id
         WHERE th.CONNECT_BY_ISCYCLE = 0)                     -- NOCYCLE
 SELECT th.*
      --, REPLICATE(' ', (th."LEVEL" - 1) * 3) + th.name AS tbl_hierarchy
   FROM tbl_hierarchy th
        JOIN tbl CONNECT_BY_ROOT ON (CONNECT_BY_ROOT.id = th.root_id)
  ORDER BY th.SYS_CONNECT_BY_PATH_name;                       -- ORDER SIBLINGS BY name


CONNECT BY features demonstrated above, with explanations:

   • Clauses
          CONNECT BY: Specifies the relationship that defines the hierarchy.
          ○


          START WITH: Specifies the root nodes.
          ○


          ORDER SIBLINGS BY: Orders results properly.
          ○


   • Parameters
          NOCYCLE: Stops processing a branch when a loop is detected. Valid hierarchies are
          ○


          Directed Acyclic Graphs, and circular references violate this construct.
   • Operators
          PRIOR: Obtains data from the node's parent.
          ○


          CONNECT_BY_ROOT: Obtains data from the node's root.
          ○


   • Pseudocolumns
          LEVEL: Indicates the node's distance from its root.
          ○


          CONNECT_BY_ISLEAF: Indicates a node without children.
          ○


          CONNECT_BY_ISCYCLE: Indicates a node with a circular reference.
          ○


   • Functions
          SYS_CONNECT_BY_PATH: Returns a flattened/concatenated representation of the
          ○


          path to the node from its root.

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
