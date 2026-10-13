# Chapter 18: EXCEPT

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 18: EXCEPT
Remarks
EXCEPT returns any distinct values from the dataset to the left of the EXCEPT operator that are not
also returned from the right dataset.


Examples
Select dataset except where values are in this other dataset

 --dataset schemas must be identical
 SELECT 'Data1' as 'Column' UNION ALL
 SELECT 'Data2' as 'Column' UNION ALL
 SELECT 'Data3' as 'Column' UNION ALL
 SELECT 'Data4' as 'Column' UNION ALL
 SELECT 'Data5' as 'Column'
 EXCEPT
 SELECT 'Data3' as 'Column'
 --Returns Data1, Data2, Data4, and Data5


Read EXCEPT online: https://riptutorial.com/sql/topic/4082/except
