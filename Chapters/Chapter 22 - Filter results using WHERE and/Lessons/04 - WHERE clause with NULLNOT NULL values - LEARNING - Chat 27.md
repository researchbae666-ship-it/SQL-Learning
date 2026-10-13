---
chat_lesson: 27
chapter: 22
source_lesson: 4
status: "understood after corrections"
record_fidelity: selected-verbatim-and-summary
sql_dialect: Microsoft SQL Server 2012
original_complete_transcript_available: false
---

# Chat Lesson 27: IS NULL

**Topic:** Find missing values  
**Mapped by topic to textbook chapter:** 22, textbook lesson 4  
**Textbook lesson file:** [04 - WHERE clause with NULLNOT NULL values.md](04%20-%20WHERE%20clause%20with%20NULLNOT%20NULL%20values.md)  
**Conversation record type:** Selected verbatim messages and faithful summaries from conversation context, not the entire unabridged transcript.

## What our lesson covered

Practiced IS NULL and the difference between a missing value (NULL) and the recorded number zero.

### Verbatim SQL submissions and recorded feedback

**Original challenge:** Retrieve only PHARMACISTNAME for pharmacists with missing YEARSEXPERIENCE, not including a recorded zero. Example LAYLA 3; OMAR NULL; HIBA 5; NOOR NULL; SARA 0.

**Verbatim first submission:**

```sql
SELECT PHARMACISTNAME
FROM PHARMACISTS
WHERE YEARSEXPERIENCE IS NULL OR 0;
```

**Assistant grade:** 8/10. `IS NULL` is correct but `OR 0` is an invalid boolean condition in SQL Server 2012 and unnecessary. Correct filter is `WHERE YEARSEXPERIENCE IS NULL;`.

**Correction challenge:** Retrieve DOCTORNAME from DOCTORS with missing AGE, excluding OMAR with AGE=0 automatically.

**Verbatim second submission:**

```sql
SELECT DOCTORNAME
FROM DOCTORS
WHERE DOCTORNAME <> OMAR
AND AGE IS NULL;
```

**Assistant grade:** 8/10. `OMAR` was unquoted, and the name exclusion was redundant. Correct query:

```sql
SELECT DOCTORNAME
FROM DOCTORS
WHERE AGE IS NULL;
```

### Verbatim follow-up questions

> IS NULL DOES NOT MATCH 0 BUT IN THE ABOVE SQL WE NEED IT TO EXCLUDE 0 HOW IS NULL COVERING IT?

**Assistant explanation:** `WHERE` keeps matching rows; rows that fail the condition are excluded automatically. `0` does not match `IS NULL`, so no extra exclusion is needed. Illustration: NULL rows are included; zero and other numeric values are excluded.

**User follow-up (opening verbatim):**

> SO HOW WOULD THE SQK QUERY LOOK LIKE WHEN THIS IS THE QUESTION

The user repeated the doctor table with MAYA 28, LINA NULL, OMAR 0, SARA NULL, HIBA 35 and requested only missing-age doctors. Correct result LINA and SARA with `WHERE AGE IS NULL`.

**Verbatim user reactions:**

> somewhat i think i get it

Then the assistant gave a final understanding check contrasting `WHERE AGE = 25` versus `AND AGE <> 0`.

> got it

**Status:** Concept understood after discussion; do not treat the earlier incorrect SQL submissions as correct. No subsequent successfully submitted `IS NULL` correction query is visible.


## Full verbatim lesson transcript

**Not yet fully recovered.** Preserve this distinction: the sections above record only the information actually retained from prior lessons. Full messages must be imported from the source chat history, not reconstructed as quotations.

## Teaching and assessment conventions

- We use Microsoft SQL Server 2012-compatible T-SQL.
- One small concept at a time, followed by one coding challenge.
- Grade actual SQL attempts line by line; distinguish SQL validity from meeting the prompt.
- A major assessment requires at least 85% to pass.
