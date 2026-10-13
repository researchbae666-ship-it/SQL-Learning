---
chat_lesson: 25
chapter: 36
source_lesson: 1
status: "studied; rubric and verbatim transcript incomplete"
record_fidelity: selected-verbatim-and-summary
sql_dialect: Microsoft SQL Server 2012
original_complete_transcript_available: false
---

# Chat Lesson 25: LIKE ends with

**Topic:** LIKE suffix wildcard  
**Mapped by topic to textbook chapter:** 36, textbook lesson 1  
**Textbook lesson file:** [01 - Match open-ended pattern.md](01%20-%20Match%20open-ended%20pattern.md)  
**Conversation record type:** Selected verbatim messages and faithful summaries from conversation context, not the entire unabridged transcript.

## What our lesson covered

Practiced LIKE '%RA' and the correction LIKE '%NA' for names ending with a given suffix.

### Verbatim user SQL submissions retained

First attempt for names ending in RA (incorrect for the stated task; prefix query):

```sql
SELECT NURSENAME
FROM NURSES
WHERE NURSENAME LIKE 'NO%';
```

**Feedback:** 7/10; syntactically valid, but matches names beginning NO rather than ending RA. The lesson emphasized wildcard position: `'%RA'` for the suffix.

Correction question: return only `NURSENAME` from `NURSES` for names ending in NA.

**Verbatim user correction:**

```sql
SELECT NURSENAME
FROM NURSES
WHERE NURSENAME LIKE '%NA';
```

**Feedback:** 10/10. Each SELECT, FROM, and WHERE line was correct; expected matches were LINA, HANA, DINA. The assistant then unlocked `LIKE '%...%'`.


## Full verbatim lesson transcript

**Not yet fully recovered.** Preserve this distinction: the sections above record only the information actually retained from prior lessons. Full messages must be imported from the source chat history, not reconstructed as quotations.

## Teaching and assessment conventions

- We use Microsoft SQL Server 2012-compatible T-SQL.
- One small concept at a time, followed by one coding challenge.
- Grade actual SQL attempts line by line; distinguish SQL validity from meeting the prompt.
- A major assessment requires at least 85% to pass.
