# Chapter 3 — Evaluation Methodologies

## The Core Idea
"Evaluation is everything." You can't improve what you can't measure.
For AI apps, evaluation is hard because outputs are open-ended.
Three main approaches:
1. **Exact metrics** (precision, recall) — for structured outputs
2. **Embedding similarity** — compare semantic meaning, not exact words
3. **AI-as-judge** — use an LLM to grade another LLM's output

## Tasks

### Task 3.1 — Define what "good" looks like
Before measuring anything, write down (in this file) what a *good* scene
extraction looks like for CuentaCuentos. Consider:
- Does it capture the most visually interesting moment?
- Does it include enough detail to generate a good image?
- Does it stay faithful to the text?
- How many scenes is the right number for a 500-word passage?

Write at least 3 criteria. These become your evaluation rubric.

### Task 3.2 — Build a manual evaluation set
Pick 5 book passages (different genres: fantasy, mystery, romance, sci-fi,
literary fiction). For each:
- Run it through your scene extraction (once the API is wired up)
- Score each extracted scene 1–5 on your rubric from Task 3.1
- Note what went wrong for low scores

Save results in `learning/eval-results.md`.

### Task 3.3 — Try AI-as-judge
Write a second Claude prompt that takes a book passage + the extracted
scenes and scores them. Ask it to explain its reasoning.
Compare its scores to your manual scores from Task 3.2.
Where do they disagree? What does that tell you?

### Task 3.4 — Track your baseline
Record the average score from Task 3.2 as your **baseline**.
Every time you improve the scene extraction prompt (Chapter 5),
re-run this eval and compare to baseline. This is how you know
if a change actually helped.
