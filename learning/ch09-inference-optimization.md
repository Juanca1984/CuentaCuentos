# Chapter 9 — Inference Optimization

## The Core Idea
Speed and cost matter in production. Key techniques: parallel calls,
caching (don't regenerate what you already have), batching, and
choosing the right model size for each task.

## Tasks

### Task 9.1 — Implement parallel image generation
By default, you might generate images sequentially (one after another).
Instead, fire all DALL-E calls simultaneously:

```typescript
const images = await Promise.all(
  scenes.map(scene => generateImage(scene.imagePrompt))
)
```

Measure the time difference between sequential and parallel for a 5-panel
storyboard. Log both times and record the improvement here.

### Task 9.2 — Add response caching
If the user submits the same passage twice, skip the API call and
return the cached result. Implement a simple in-memory cache using a Map:

```typescript
const cache = new Map<string, Scene[]>()
// key = hash of the input text
```

For persistent caching across sessions, explore Redis or Vercel KV.

### Task 9.3 — Track cost per generation
Add logging to every API call that records:
- Model used
- Input token count
- Output token count
- Estimated cost

Log to the console in development. Calculate:
- Average cost per storyboard generation
- Projected monthly cost at 100 users/day generating 2 storyboards each

### Task 9.4 — Profile your slowest step
Use `console.time()` and `console.timeEnd()` around each major step:
- Scene extraction (Claude call)
- Image generation (all DALL-E calls, parallel)
- Total time from submit to storyboard visible

Which step is the bottleneck? What would you optimize first?
