# CuentaCuentos

Paste a book fragment. Get a comic-style storyboard of AI-generated images.
Built to help visualize stories — and to learn AI engineering along the way.

## Tech Stack
- **Framework:** Next.js 14 (App Router)
- **Styling:** Tailwind CSS
- **Scene extraction:** Claude API (Anthropic)
- **Image generation:** DALL-E 3 (OpenAI)
- **Deployment:** Vercel

## Architecture

```
Book fragment → Claude (extract scenes) → DALL-E 3 (generate image per scene) → Storyboard grid
```

## Learning Roadmap
See the [/learning](./learning/) folder — one file per chapter of *AI Engineering* by Chip Huyen,
each with hands-on tasks tied to this project.

## Setup (coming soon)
