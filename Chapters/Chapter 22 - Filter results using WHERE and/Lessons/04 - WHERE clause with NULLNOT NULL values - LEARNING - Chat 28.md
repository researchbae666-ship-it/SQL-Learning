---
chat_lesson: 28
chapter: 22
source_lesson: 4
status: "introduced; practice pending"
record_fidelity: selected-verbatim-and-summary
sql_dialect: Microsoft SQL Server 2012
original_complete_transcript_available: false
---

# Chat Lesson 28: IS NOT NULL

**Topic:** Find recorded values  
**Mapped by topic to textbook chapter:** 22, textbook lesson 4  
**Textbook lesson file:** [04 - WHERE clause with NULLNOT NULL values.md](04%20-%20WHERE%20clause%20with%20NULLNOT%20NULL%20values.md)  
**Conversation record type:** Selected verbatim messages and faithful summaries from conversation context, not the entire unabridged transcript.

## What our lesson covered

Introduced IS NOT NULL; it matches recorded values including zero. A pharmacist coding challenge was given but no submitted solution is visible yet.

### Teaching preserved from the visible chat

**Assistant introduced:** `IS NULL` finds missing values; `IS NOT NULL` finds values that are not missing, including `0`.

```sql
SELECT DOCTORNAME
FROM DOCTORS
WHERE AGE IS NOT NULL;
```

**Challenge issued:** Retrieve only `PHARMACISTNAME` from `PHARMACISTS` where `YEARSEXPERIENCE IS NOT NULL`. Data: LAYLA 3, OMAR NULL, HIBA 0, NOOR NULL, SARA 5. Expected rows: LAYLA, HIBA, SARA.

**Submission status:** Not yet submitted or graded in the visible conversation. The user switched to GitHub tracking setup. This lesson must not be marked passed.


## Full verbatim lesson transcript

**Not yet fully recovered.** Preserve this distinction: the sections above record only the information actually retained from prior lessons. Full messages must be imported from the source chat history, not reconstructed as quotations.

## Teaching and assessment conventions

- We use Microsoft SQL Server 2012-compatible T-SQL.
- One small concept at a time, followed by one coding challenge.
- Grade actual SQL attempts line by line; distinguish SQL validity from meeting the prompt.
- A major assessment requires at least 85% to pass.
