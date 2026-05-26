# Chapter 1 — Completed Tasks

## Task 1.1 — Architecture Diagram

Architecture diagram drawn before writing any code, showing the full data flow:
user input → Claude (scene extraction) → DALL-E 3 (image generation) → storyboard grid.

<img width="1073" height="242" alt="Captura de pantalla 2026-05-25 a la(s) 3 03 41 p m" src="https://github.com/user-attachments/assets/5984fa92-cc29-47eb-acf5-896395627a7d" />
<img width="1213" height="226" alt="Captura de pantalla 2026-05-25 a la(s) 3 03 32 p m" src="https://github.com/user-attachments/assets/6a4c7b64-1b2b-4c8d-8813-b9dcfd1102e2" />

**Data flow (text description):**
1. User pastes a book passage (text) or uploads a photo of a book page (image)
2. Claude Sonnet 4.6 receives the input and extracts 4–8 key scenes as structured JSON
3. Each scene has a `caption` (what's happening) and an `imagePrompt` (rich visual description)
4. DALL-E 3 generates one image per scene — all calls fire in parallel
5. The storyboard grid renders with each image and its caption below

---

## Task 1.2 — AI Model Inventory

**Correction:** "Claude Vision" and "Claude Sonnet" are the same model. Claude Sonnet 4.6
has multimodal capability built in — one API call handles both image understanding
and text generation depending on what you pass it. Listing them separately would
mean two API calls and double the cost for no benefit.

| Model | Role | Input | Output | Replaceable with |
| :--- | :--- | :--- | :--- | :--- |
| **Claude Sonnet 4.6** | Extract scenes from passage (text or photo of book page) | Text or Image | Scene list JSON | GPT-4o, Gemini 1.5 Pro |
| **DALL-E 3** | Generate one image per scene | Text prompt | Image | Flux, Stable Diffusion via Replicate |

---

## Task 1.3 — Project Scaffold

Initialized Next.js 16.2.6 with TypeScript, Tailwind CSS v4, App Router, and ESLint.

```bash
npx create-next-app@latest . --typescript --tailwind --app --no-src-dir --eslint --yes
```

Key decisions:
- **App Router** over Pages Router — the current standard, better for server components
- **Tailwind v4** — included by default with Next.js 16, no separate config file needed
- **No `/src` dir** — keeps the structure flat and easier to navigate for a solo project

---

## Task 1.4 — Product Spec

CuentaCuentos is for readers who struggle to visualize unfamiliar settings — paste
any book passage and get a comic-style storyboard of AI-generated scenes, so your
imagination has a base to build from instead of starting from nothing.
