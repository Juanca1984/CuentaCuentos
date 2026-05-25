# Chapter 7 — Fine-tuning

## The Core Idea
Fine-tuning trains a model further on your specific data to improve
performance on a narrow task. It's expensive, requires data, and should
only be considered *after* prompt engineering and RAG have been exhausted.
Rule: prompt first, RAG second, finetune third.

## Tasks

### Task 7.1 — Evaluate: do you need fine-tuning?
Answer these questions honestly:
- Have you exhausted prompt engineering? (Chapter 5 tasks done?)
- Do you have at least 100 high-quality input/output examples?
- Is the quality gap large enough to justify the cost?

For most v1 applications, the answer is no. Document your assessment here.

### Task 7.2 — Identify the failure mode fine-tuning would fix
Review your eval results from Chapter 3. Is there a *consistent pattern*
of failure? Examples:
- Claude always picks action scenes, never quiet emotional moments
- Image prompts are always too literal, never impressionistic

If you find a consistent failure, that's a candidate for fine-tuning.

### Task 7.3 — Understand the cost
Look up the current pricing for:
- OpenAI fine-tuning (GPT-4o mini)
- Anthropic fine-tuning (if available)

Calculate: if you had 200 training examples averaging 500 tokens each,
what would one fine-tuning run cost? What about inference cost after?

### Task 7.4 — Stretch: experiment with image style
If you want consistent visual style across panels, explore:
- Replicate's API for running fine-tuned Stable Diffusion models
- Look at existing LoRA models trained on specific art styles
- Pick one that matches the aesthetic you want for CuentaCuentos

This is practical fine-tuning: using someone else's fine-tuned model
rather than training your own.
