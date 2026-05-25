# Chapter 8 — Dataset Engineering

## The Core Idea
Data quality beats data quantity. Your own app's outputs — especially the
ones users rate as good or bad — are your most valuable dataset.
AI-powered data synthesis can help generate training data at scale.

## Tasks

### Task 8.1 — Build your first dataset
Create a file `learning/dataset/fragments.jsonl` where each line is:
```json
{"input": "book passage here", "output": [{"caption": "...", "imagePrompt": "..."}], "quality": 4}
```
Collect at least 20 examples. Include a mix of genres and quality levels.

### Task 8.2 — Analyze your dataset
After collecting 20 examples, answer:
- Which genres produce the best image prompts?
- Which genres produce the worst?
- What's the average number of scenes extracted per 500 words?
- What's the most common failure pattern?

Write your analysis in `learning/dataset/analysis.md`.

### Task 8.3 — AI-powered data synthesis
Use Claude to generate 10 more synthetic book passages with their
ideal scene extractions. Prompt:
*"Write a 200-word fantasy book passage and then provide the ideal
scene extraction in JSON format."*

Add these to your dataset. Label them as synthetic.

### Task 8.4 — Design a data collection flywheel
Once the app has real users, every generation is a data point.
Design (in writing) how you would:
- Log every extraction + image generation
- Capture user feedback (thumbs up/down)
- Use negative feedback to flag low-quality extractions for review

This is the data flywheel that makes the product better over time.
