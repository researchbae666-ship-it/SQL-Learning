# SQL Learning 👑

A source-grounded SQL study archive, organized by textbook chapter and by the *actual topic taught*, rather than forcing our conversations into chapter order.

## Start here

- [64 textbook chapters](Chapters/) — each has an unchanged `CHAPTER.md`.
- [244 textbook lesson files](Chapters/) — grouped inside each chapter's `Lessons/` folder. Chapter-level `LESSONS.md` files provide lesson indexes.
- [Learning index: previously studied lessons](LEARNING-INDEX.md) — maps **28 chat lessons** to their related textbook lesson files, with separate `- LEARNING - Chat NN.md` records.
- [Foundation exam history](Assessments/Foundation%20Exam%2001%20-%20History.md) — initial 82.5%, targeted retake 95%; 85% passing threshold.
- [Complete publisher PDF](Source/SQL-Textbook-Publisher.pdf) — 221-page ebook in the repository; [source-version notes](Source/README.md).

## File-pair convention

For a topic we've studied:

```text
Chapters/Chapter NN - Topic/
├── CHAPTER.md                # Chapter from the textbook
├── LESSONS.md                # Chapter lesson index
└── Lessons/
    ├── 01 - Topic.md         # Textbook lesson
    └── 01 - Topic - LEARNING - Chat XX.md
                                 # Our teaching conversation and learner attempts
```

Multiple bite-sized chat lessons may map to the **same textbook lesson**, in which case each has its own distinct `- LEARNING - Chat XX.md` record.

## Truthful transcript handling

- Chat lessons 1–24 are recoverable topic summaries, **not complete message-by-message transcripts**.
- Chat lessons 25–28 preserve selected verbatim examples/questions and summaries; full transcripts are not all recoverable from the available conversation context.
- We keep original user SQL, assistant grading, corrections, and exam results only where supported by recovered information. No made-up transcript wording.
- The historical Chat Lesson 10 assignment is provisional (topic covered, exact numbering not verified).
- Chapter lesson statuses are *planned* until current learning progress is separately reconciled; the existence of a study note does not mean an 85% mastery pass.
- Teaching and exercise solutions target **Microsoft SQL Server 2012**; the reference ebook covers multiple SQL dialects, so not every original example runs unchanged in SSMS.

## Original PDF provenance

The full 221-page publisher edition is archived in `Source/SQL-Textbook-Publisher.pdf`. The user's uploaded PDF was also 221 pages but has a **different binary SHA-256**; the publisher copy is not represented as byte-identical. Exact hashes are in [Source/README.md](Source/README.md).

## Attribution

*SQL* — unofficial educational ebook compiled from Stack Overflow Documentation contributor content, hosted at [riptutorial.com/sql](https://riptutorial.com/sql) and released under CC BY-SA. Read the PDF's credits for contributor details. This is not an official Stack Overflow SQL Server textbook.
