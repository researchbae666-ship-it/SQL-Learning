# Chapter 48: SQL CURSOR

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 48: SQL CURSOR
Examples
Example of a cursor that queries all rows by index for each database

Here, a cursor is used to loop through all databases.
Futhermore, a cursor from dynamic sql is used to query each database returned by the first cursor.

This is to demonstrate the connection-scope of a cursor.

 DECLARE @db_name nvarchar(255)
 DECLARE @sql nvarchar(MAX)

 DECLARE @schema nvarchar(255)
 DECLARE @table nvarchar(255)
 DECLARE @column nvarchar(255)




 DECLARE db_cursor CURSOR FOR
 SELECT name FROM sys.databases



 OPEN db_cursor
 FETCH NEXT FROM db_cursor INTO @db_name

 WHILE @@FETCH_STATUS = 0
 BEGIN
     SET @sql = 'SELECT * FROM ' + QUOTENAME(@db_name) + '.information_schema.columns'
     PRINT ''
     PRINT ''
     PRINT ''
     PRINT @sql
     -- EXECUTE(@sql)




     -- For each database

     DECLARE @sqlstatement nvarchar(4000)
     --move declare cursor into sql to be executed
     SET @sqlstatement = 'DECLARE columns_cursor CURSOR FOR SELECT TABLE_SCHEMA, TABLE_NAME,
 COLUMN_NAME FROM ' + QUOTENAME(@db_name) + '.information_schema.columns ORDER BY TABLE_SCHEMA,
 TABLE_NAME, ORDINAL_POSITION'




     EXEC sp_executesql @sqlstatement



     OPEN columns_cursor
     FETCH NEXT FROM columns_cursor
     INTO @schema, @table, @column




       WHILE @@FETCH_STATUS = 0
       BEGIN
           PRINT @schema + '.' + @table + '.' + @column
           --EXEC asp_DoSomethingStoredProc @UserId

       FETCH NEXT FROM columns_cursor --have to fetch again within loop
       INTO @schema, @table, @column

       END
       CLOSE columns_cursor
       DEALLOCATE columns_cursor

       -- End for each database




       FETCH NEXT FROM db_cursor INTO @db_name
 END

 CLOSE db_cursor
 DEALLOCATE db_cursor


Read SQL CURSOR online: https://riptutorial.com/sql/topic/8895/sql-cursor
