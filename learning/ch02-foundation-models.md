# Chapter 2 — Foundation Models

## The Core Idea
Foundation models (Claude, GPT-4, DALL-E, Stable Diffusion) are trained on
massive datasets and can generalize across many tasks. Understanding *how*
they were trained helps you understand *what they're good at* — and where
they'll fail.

Key concepts: transformers, RLHF (Reinforcement Learning from Human Feedback),
scaling laws, multimodal models.

## Tasks

### Task 2.1 — Read the model cards
Read the official documentation for both models you'll use:
- Claude: https://docs.anthropic.com/en/docs/about-claude/models
- DALL-E 3: https://platform.openai.com/docs/models

For each, write down:
- What kind of data was it trained on?
- What tasks is it explicitly good at?
- What are its known limitations?

### Task 2.2 — Test Claude's narrative understanding
Without any code — use the Claude.ai chat interface directly.
Paste a short paragraph from a book you like and ask:
*"Extract the 3 most visually interesting scenes from this passage, describe each in detail."*

Then ask it again but add: *"Focus on lighting, mood, and setting."*
Compare the results. Notice what changes when you add specificity.

### Task 2.3 — Test DALL-E's scene rendering
Using the OpenAI playground (platform.openai.com/playground):
Generate images from 3 different prompts derived from the same book scene.
Vary the style descriptor (realistic, illustrated, pencil sketch).
Screenshot and save to `learning/dalle-experiments/`.

### Task 2.4 — Connect the APIs
Set up your `.env.local` file:
```
ANTHROPIC_API_KEY=your_key_here
OPENAI_API_KEY=your_key_here
```
Install the SDKs:
```bash
npm install @anthropic-ai/sdk openai
```
Write a simple test script (`lib/test-apis.ts`) that makes one call to each
API and logs the response. Confirm both are working before building the UI.
