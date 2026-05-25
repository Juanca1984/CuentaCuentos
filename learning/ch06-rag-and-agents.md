# Chapter 6 — RAG & Agents

## The Core Idea
**RAG (Retrieval-Augmented Generation):** Give the model access to external
knowledge it wasn't trained on, retrieved at query time. Reduces hallucination,
keeps information fresh.

**Agents:** AI that can plan multi-step tasks and use tools (search, APIs,
code execution) autonomously to complete a goal.

## Tasks

### Task 6.1 — Understand why RAG matters here
Write a paragraph answering: What information does Claude *not* have when
extracting scenes from a book fragment?
Example: it doesn't know what characters look like, the world's visual style,
or author-specific tone. RAG is the solution.

### Task 6.2 — Build a "Character Bible" feature (RAG)
Let the user paste a character description block before generating the storyboard.
Example: "Elena has red hair, green eyes, and wears a brown leather cloak."

When extracting scenes, include this context in the Claude prompt so that
image prompts reference character appearance correctly.
This is manual RAG — the user retrieves and provides the context.

### Task 6.3 — Test consistency
With and without the character bible:
- Generate a 4-panel storyboard from the same passage
- Compare how consistently characters appear across panels
- Note: DALL-E doesn't guarantee consistency — document this limitation

### Task 6.4 — Research agentic approaches (stretch)
Research how an agent could automatically retrieve book context:
- Search Wikipedia for the book title
- Extract character descriptions
- Feed them into the prompt

Write a design doc (just text, no code required) in `learning/agent-design.md`
describing how you would build this agent using the Anthropic tool_use API.
