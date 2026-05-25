# Chapter 10 — Architecture & User Feedback

## The Core Idea
Production AI systems need to close the feedback loop: collect signals
from users, use them to improve prompts and models, and compound that
advantage over time. User feedback is your most valuable data asset.

## Tasks

### Task 10.1 — Add panel feedback buttons
Add a thumbs up 👍 and thumbs down 👎 button to each storyboard panel.
When clicked, log the feedback with:
- The input text (hashed for privacy)
- The scene caption
- The image prompt that was used
- The rating (positive/negative)

Store in localStorage for now.

### Task 10.2 — Connect to a simple database
Set up a free Supabase project (supabase.com).
Create a `feedback` table:
```sql
create table feedback (
  id uuid default gen_random_uuid(),
  created_at timestamp default now(),
  input_hash text,
  caption text,
  image_prompt text,
  rating text, -- 'positive' or 'negative'
  art_style text
);
```
Wire up the thumbs up/down buttons to insert rows via the Supabase client.

### Task 10.3 — Analyze your first 50 feedback entries
Once you have real usage data, query for all negative feedback:
- What kinds of captions get thumbs down?
- Which art styles get the most thumbs down?
- Is there a pattern in the image prompts that fail?

Use this analysis to update your scene extraction prompt.

### Task 10.4 — Design your competitive moat
Write a short essay (3–5 paragraphs) in this file answering:
*"If CuentaCuentos got 10,000 users, what data would we have that no
competitor could easily replicate?"*

Think about: the feedback dataset, the book genre coverage, the styles
users prefer. This is the core of Chip Huyen's argument: proprietary
data is the durable competitive advantage in AI products.
