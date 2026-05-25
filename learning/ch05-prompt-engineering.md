# Chapter 5 — Prompt Engineering

## The Core Idea
Prompt engineering is the highest-leverage skill in AI engineering.
Small changes in phrasing dramatically change output quality.
Key techniques: clear instructions, few-shot examples, chain-of-thought,
task decomposition, output format constraints, defensive prompting.

## Tasks

### Task 5.1 — Write prompt v1
Write the initial system prompt for scene extraction. It should instruct
Claude to:
- Identify the most visually interesting scenes
- Return structured JSON (array of objects with `caption` and `imagePrompt`)
- Keep captions short (under 15 words)
- Make image prompts rich and detailed

Save it in `lib/prompts/extract-scenes-v1.ts`.

### Task 5.2 — Add few-shot examples
Improve v1 by adding 2 example input/output pairs to the prompt
(one fantasy scene, one realistic scene).
Save as `lib/prompts/extract-scenes-v2.ts`.
Re-run your eval from Task 3.2. Did scores improve?

### Task 5.3 — Test edge cases
Try these adversarial inputs and note how the prompt handles them:
- A passage of pure dialogue with no action
- A poem
- A passage in Spanish
- A very short input (1 sentence)
- A very long input (3000 words)

Fix any failures by updating the prompt. Document what broke and how you fixed it.

### Task 5.4 — Add defensive prompting
What if a user pastes something that isn't a book (source code, a recipe,
a list of names)? Add a guard to the prompt that:
- Detects non-narrative input
- Returns a structured error response instead of hallucinating scenes

Test it. Does it work reliably?

### Task 5.5 — Style injection
The user can select an art style (realistic, anime, sketch, etc.).
Update the prompt or post-processing logic to append the style to every
`imagePrompt` in a consistent, effective way.
Test that the style actually changes the DALL-E output visually.
