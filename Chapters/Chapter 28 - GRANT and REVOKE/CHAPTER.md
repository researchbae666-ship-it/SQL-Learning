# Chapter 28: GRANT and REVOKE

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 28: GRANT and REVOKE
Syntax
   • GRANT [privilege1] [, [privilege2] ... ] ON [table] TO [grantee1] [, [grantee2] ... ] [ WITH
     GRANT OPTION ]
   • REVOKE [privilege1] [, [privilege2] ... ] ON [table] FROM [grantee1] [, [grantee2] ... ]


Remarks
Grant permissions to users. If the WITH GRANT OPTION is specified, the grantee additionally gains the
privilege to grant the given permission or revoke previously granted permissions.


Examples
Grant/revoke privileges

 GRANT SELECT, UPDATE
 ON Employees
 TO User1, User2;


Grant User1 and User2 permission to perform SELECT and UPDATE operations on table Employees.


 REVOKE SELECT, UPDATE
 ON Employees
 FROM User1, User2;


Revoke from User1 and User2 the permission to perform SELECT and UPDATE operations on table
Employees.

Read GRANT and REVOKE online: https://riptutorial.com/sql/topic/5574/grant-and-revoke
