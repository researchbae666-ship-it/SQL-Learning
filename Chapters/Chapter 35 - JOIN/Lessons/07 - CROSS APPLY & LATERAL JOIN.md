---
lesson_id: C35-L07
chapter: 35
lesson: 7
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C35-L07: CROSS APPLY & LATERAL JOIN

## Textbook excerpt

CROSS APPLY & LATERAL JOIN

A very interesting type of JOIN is the LATERAL JOIN (new in PostgreSQL 9.3+),
which is also known as CROSS APPLY/OUTER APPLY in SQL-Server & Oracle.

The basic idea is that a table-valued function (or inline subquery) gets applied for every row you
join.

This makes it possible to, for example, only join the first matching entry in another table.
The difference between a normal and a lateral join lies in the fact that you can use a column that
you previously joined in the subquery that you "CROSS APPLY".

Syntax:

PostgreSQL 9.3+



https://riptutorial.com/                                                            Steve Nouri   109

      left | right | inner JOIN LATERAL

SQL-Server:

      CROSS | OUTER APPLY

INNER JOIN LATERAL is the same as CROSS APPLY
and LEFT JOIN LATERAL is the same as OUTER APPLY

Example usage (PostgreSQL 9.3+):

 SELECT * FROM T_Contacts

 --LEFT JOIN T_MAP_Contacts_Ref_OrganisationalUnit ON MAP_CTCOU_CT_UID = T_Contacts.CT_UID AND
 MAP_CTCOU_SoftDeleteStatus = 1
 --WHERE T_MAP_Contacts_Ref_OrganisationalUnit.MAP_CTCOU_UID IS NULL -- 989



 LEFT JOIN LATERAL
 (
     SELECT
          --MAP_CTCOU_UID
          MAP_CTCOU_CT_UID
         ,MAP_CTCOU_COU_UID
         ,MAP_CTCOU_DateFrom
         ,MAP_CTCOU_DateTo
    FROM T_MAP_Contacts_Ref_OrganisationalUnit
    WHERE MAP_CTCOU_SoftDeleteStatus = 1
    AND MAP_CTCOU_CT_UID = T_Contacts.CT_UID

     /*
     AND
     (
           (__in_DateFrom <= T_MAP_Contacts_Ref_OrganisationalUnit.MAP_KTKOE_DateTo)
           AND
           (__in_DateTo >= T_MAP_Contacts_Ref_OrganisationalUnit.MAP_KTKOE_DateFrom)
     )
     */
    ORDER BY MAP_CTCOU_DateFrom
    LIMIT 1
 ) AS FirstOE


And for SQL-Server

 SELECT * FROM T_Contacts

 --LEFT JOIN T_MAP_Contacts_Ref_OrganisationalUnit ON MAP_CTCOU_CT_UID = T_Contacts.CT_UID AND
 MAP_CTCOU_SoftDeleteStatus = 1
 --WHERE T_MAP_Contacts_Ref_OrganisationalUnit.MAP_CTCOU_UID IS NULL -- 989

 -- CROSS APPLY -- = INNER JOIN
 OUTER APPLY    -- = LEFT JOIN
 (
     SELECT TOP 1
          --MAP_CTCOU_UID
          MAP_CTCOU_CT_UID
         ,MAP_CTCOU_COU_UID
         ,MAP_CTCOU_DateFrom




         ,MAP_CTCOU_DateTo
    FROM T_MAP_Contacts_Ref_OrganisationalUnit
    WHERE MAP_CTCOU_SoftDeleteStatus = 1
    AND MAP_CTCOU_CT_UID = T_Contacts.CT_UID

     /*
     AND
     (
           (@in_DateFrom <= T_MAP_Contacts_Ref_OrganisationalUnit.MAP_KTKOE_DateTo)
           AND
           (@in_DateTo >= T_MAP_Contacts_Ref_OrganisationalUnit.MAP_KTKOE_DateFrom)
     )
     */
    ORDER BY MAP_CTCOU_DateFrom
 ) AS FirstOE

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
