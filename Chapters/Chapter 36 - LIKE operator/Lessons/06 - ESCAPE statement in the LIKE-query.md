---
lesson_id: C36-L06
chapter: 36
lesson: 6
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C36-L06: ESCAPE statement in the LIKE-query

## Textbook excerpt

ESCAPE statement in the LIKE-query



If you implement a text-search as LIKE-query, you usually do it like this:

 SELECT *
 FROM T_Whatever
 WHERE SomeField LIKE CONCAT('%', @in_SearchText, '%')


However, (apart from the fact that you shouldn't necessarely use LIKE when you can use fulltext-
search) this creates a problem when somebody inputs text like "50%" or "a_b".

So (instead of switching to fulltext-search), you can solve that problem using the LIKE-escape
statement:

 SELECT *
 FROM T_Whatever
 WHERE SomeField LIKE CONCAT('%', @in_SearchText, '%') ESCAPE '\'


That means \ will now be treated as ESCAPE character. This means, you can now just prepend \
to every character in the string you search, and the results will start to be correct, even when the
user enters a special character like % or _.

e.g.

 string stringToSearch = "abc_def 50%";
 string newString = "";
 foreach(char c in stringToSearch)
      newString += @"\" + c;

 sqlCmd.Parameters.Add("@in_SearchText", newString);
 // instead of sqlCmd.Parameters.Add("@in_SearchText", stringToSearch);


Note: The above algorithm is for demonstration purposes only. It will not work in cases where 1
grapheme consists out of several characters (utf-8). e.g. string stringToSearch = "Les
Mise\u0301rables"; You'll need to do this for each grapheme, not for each character. You should
not use the above algorithm if you're dealing with Asian/East-Asian/South-Asian languages. Or
rather, if you want correct code to begin with, you should just do that for each graphemeCluster.

See also ReverseString, a C# interview-question

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
