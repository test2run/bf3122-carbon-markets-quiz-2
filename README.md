# BF3122 — Applied Concept Quiz 2

A self-quizzing tool for **BF3122 Carbon Markets**, covering Weeks 6, 9 and 10 (Quiz 2 scope).
The Quiz 1 version (Weeks 1–4) lives at [bf3122-carbon-markets-quiz](https://github.com/test2run/bf3122-carbon-markets-quiz).

**99 multiple-choice questions.** Every one tests applied or conceptual understanding: working out an
airline's CORSIA obligation on a given route, classifying a company's claim, picking the ERPA clause or
insurance product for a stated risk, or judging which law governs a disputed credit. No question asks you
to recall a statistic for its own sake. Where numbers appear, they are scenario inputs to reason with.

Options are written to compete with each other. The correct answer is the longest option about as often
as it is the shortest, so option length gives nothing away.

## Using it

Pick topics (or a week), choose **Instant** feedback for learning or **Exam** mode to simulate the real
thing, and go. You can navigate backwards, as in the actual quiz. At the end you get a per-topic
breakdown and a full review with a rationale for *every* option, including why the near-miss
distractors are only partly true.

Keyboard: <kbd>1</kbd>–<kbd>4</kbd> to answer, <kbd>←</kbd> <kbd>→</kbd> to move.

## Topics

Mapped to the recap slide that closes each lecture:

| # | Topic | Week | Qs |
|---|---|---|---|
| 1 | Aviation emissions & ICAO's role | 6 | 7 |
| 2 | CORSIA design & offsetting obligations | 6 | 12 |
| 3 | Eligible units, fuels, criticisms & the EU | 6 | 12 |
| 4 | Claims, greenwashing & claim vocabulary | 9 | 11 |
| 5 | VCMI & SBTi standards | 9 | 14 |
| 6 | Government guidance & legal nature of credits | 9 | 11 |
| 7 | Transaction pathways | 10 | 12 |
| 8 | Risk, contracts & insurance | 10 | 20 |

Content is drawn from the lecture slides and their annotations. Material flagged in class as "must
know" or "may be tested", boxed in red, or starred gets more weight. Material marked NT (not tested) is
left out.

## Files

```
index.html       markup + styles
app.js           quiz logic (vanilla JS, no dependencies)
questions.json   all content
```

To edit or add a question, edit `questions.json` only. Each entry:

```jsonc
{
  "id": "q001",
  "topic": "t1",            // matches topics[].id
  "week": 6,
  "difficulty": 2,          // 1 core · 2 standard · 3 hard
  "skill": "apply",         // apply | compare | predict | diagnose
  "stem": "…",
  "options": ["…","…","…","…"],
  "answer": 1,              // 0-based index into options
  "rationales": ["…","…","…","…"],   // one per option, same order
  "takeaway": "One-line principle.",
  "source": "W6 p13"        // slide provenance
}
```

The app reads the file at load, so a committed edit is live on the next refresh.

Run locally with any static server (opening `index.html` from disk will fail, because browsers block
`fetch` on `file://`):

```bash
python -m http.server 8000
```
