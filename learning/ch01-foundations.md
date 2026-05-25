# Chapter 1 — Foundations of AI Engineering

## The Core Idea
AI engineering is about building products on top of foundation models —
not training models from scratch. You orchestrate existing AI capabilities
(Claude, DALL-E, Whisper) into useful applications.

The key shift: your job is to design the *system around the model*,
not the model itself.

## Tasks

### Task 1.1 — Map the CuentaCuentos architecture
Before writing any code, draw (on paper or in a tool like Excalidraw) the full
data flow of the app:
- What does the user input?
- What does Claude receive and return?
- What does DALL-E receive and return?
- What does the user see?

Save a photo or export of your diagram as `learning/architecture.png`.

### Task 1.2 — Identify the AI components
List every AI model this app uses or could use. For each, write:
- What it does in the app
- What its input and output types are
- Whether it could be swapped for a different model

Example format:

| Model | Role | Input | Output | Replaceable with |
|-------|------|-------|--------|-----------------|

### Task 1.3 — Create the project scaffold
Initialize the Next.js app inside this folder:
```bash
npx create-next-app@latest . --typescript --tailwind --app --no-src-dir
```
Commit it as the project baseline.

### Task 1.4 — Write a one-paragraph product spec
In your own words, write what CuentaCuentos does, who it's for, and what
problem it solves. Add it to the README.md. Good specs force clarity.
