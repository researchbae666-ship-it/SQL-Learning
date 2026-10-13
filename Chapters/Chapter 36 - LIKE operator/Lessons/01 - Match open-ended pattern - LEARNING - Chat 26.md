---
chat_lesson: 26
chapter: 36
source_lesson: 1
status: "studied; rubric and verbatim transcript incomplete"
record_fidelity: selected-verbatim-and-summary
sql_dialect: Microsoft SQL Server 2012
original_complete_transcript_available: false
---

# Chat Lesson 26: LIKE contains

**Topic:** LIKE substring wildcard  
**Mapped by topic to textbook chapter:** 36, textbook lesson 1  
**Textbook lesson file:** [01 - Match open-ended pattern.md](01%20-%20Match%20open-ended%20pattern.md)  
**Conversation record type:** Selected verbatim messages and faithful summaries from conversation context, not the entire unabridged transcript.

## What our lesson covered

Practiced LIKE '%AN%' for names containing AN anywhere.

### Verbatim chat excerpts retained

**Assistant teaching point:** `'SA%'` begins with SA; `'%NA'` ends with NA; `'%AR%'` contains AR anywhere. Challenge: names containing AN, with example table SARA, HANA, DANA, LINA, OMAR.

**Verbatim user message:**

> Grade my SQL Server 2012 LIKE query line by line. It must retrieve only NURSENAME from NURSES for names containing AN anywhere, using % on both sides. If correct, unlock the next small SQL concept from my PDF and give one coding challenge.
>
> My SQL:

```sql
SELECT NURSENAME
FROM NURSES
WHERE NURSENAME LIKE '%AN%';
```

**Assistant grading:** 10/10, all three lines and statement terminator correct; expected results HANA and DANA. Lesson 27, IS NULL, was introduced next.


## Full verbatim lesson transcript

**Not yet fully recovered.** Preserve this distinction: the sections above record only the information actually retained from prior lessons. Full messages must be imported from the source chat history, not reconstructed as quotations.

## Teaching and assessment conventions

- We use Microsoft SQL Server 2012-compatible T-SQL.
- One small concept at a time, followed by one coding challenge.
- Grade actual SQL attempts line by line; distinguish SQL validity from meeting the prompt.
- A major assessment requires at least 85% to pass.
