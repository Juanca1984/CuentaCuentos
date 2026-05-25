# Chapter 4 — Model Selection & Assessment

## The Core Idea
Public benchmarks don't tell you which model is best *for your task*.
You need to build your own eval pipeline and test models against your
specific use case. Cost, latency, and quality must all be weighed together.

## Tasks

### Task 4.1 — Compare Claude models on scene extraction
Run the same 5 passages from Task 3.2 through two Claude models:
- `claude-haiku-4-5` (fast, cheap: ~$0.25/M input tokens)
- `claude-sonnet-4-6` (smarter: ~$3/M input tokens)

Score each output using your rubric. Build a comparison table:

| Passage | Haiku score | Sonnet score | Haiku cost | Sonnet cost |
|---------|-------------|--------------|------------|-------------|

### Task 4.2 — Calculate the real cost difference
For a typical session (user pastes a 1000-word chapter):
- Estimate token count (1000 words ≈ 1300 tokens)
- Calculate cost for Haiku vs. Sonnet
- If you had 100 daily users, what's the monthly cost difference?

Write up your finding: is the quality worth the cost for this use case?

### Task 4.3 — Choose your production model
Based on Tasks 4.1 and 4.2, decide which model to use for the app.
Document your decision and reasoning in this file under a "Decision" section.
This is a real engineering decision — own it with data.

### Task 4.4 — Compare image generation models
Test the same scene prompt through:
- DALL-E 3 (OpenAI)
- Stable Diffusion XL via Replicate (cheaper)

Compare quality, cost, and speed. Document in `learning/image-model-comparison.md`.
