---
name: catchkey
description: >
  Reverse-engineer any image into detailed AI prompts for Midjourney, Stable Diffusion,
  DALL·E, Flux, and ComfyUI. Use this skill whenever a user shares, references, or uploads
  an image and wants to know how to recreate it, what prompt generated it, or how to describe
  it for AI generation. This includes when users say "extract the prompt", "reverse engineer
  this image", "what prompt would create this",
  "write a prompt to recreate this", "what style is this image", or when they ask to convert
  a visual reference into text for any AI image generator. Whenever an image is involved and
  the user wants a prompt out of it, use this skill. Do not use for generic prompt writing
  tips, image editing/OCR tasks, or building prompt-generation tools from scratch.
---

# Image Prompt Extractor

Transform any image into a high-quality, platform-optimized AI generation prompt through systematic visual analysis.

## When this skill fires

A user has shared an image and wants to know what prompt generated it, or how to recreate something visually similar. They might phrase this in many ways — casually ("what's the prompt behind this?"), technically ("reverse engineer this MJ image"), or by simply uploading an image and asking "how do I make this?".

If the intent is clear even from an indirect ask, jump in. Better to offer a prompt and be told "I didn't need that" than to stay silent when the user needs help.

---

## Workflow

### Step 1: Read and observe the image

Use the Read tool to examine the image. Before writing anything, spend time really looking. A rushed analysis produces generic prompts; a careful one captures what makes the image distinctive.

Observe systematically across these dimensions:

**Subject & hierarchy** — What's the primary focal point? What supports it? What's the background context? Note relationships between elements, not just a list of objects.

**Style & medium** — Is this a photograph, a 3D render, an oil painting, anime, vector illustration, pixel art, watercolor, charcoal sketch, or something else hybrid? Be specific — "anime" and "Studio Ghibli cel animation" are very different. Read `references/visual-analysis-guide.md` if you need help with style taxonomy.

**Composition & framing** — Angle (eye-level, low, high, bird's-eye, worm's-eye), depth of field (shallow bokeh vs deep focus), crop (full-body, headshot, wide landscape), symmetry, rule of thirds, leading lines, negative space.

**Lighting & atmosphere** — Source direction, quality (hard/soft shadows), color temperature, mood (ethereal, moody, cheerful, mysterious), any volumetric or rim lighting effects.

**Color & tonality** — Dominant palette, saturation level, contrast ratio, color harmony (complementary, analogous, monochromatic), any grading style (teal-orange, pastel, desaturated).

**Details & textures** — What gives the image its tactile quality? Skin pores, fabric weave, rust, water droplets, film grain, chromatic aberration, lens flare?

**Technical markers** — Resolution, aspect ratio, any visible AI artifacts (inconsistent hands, merging details, impossible reflections), or photographic indicators (natural noise, EXIF-style characteristics).

### Step 2: Assess the image source

Based on your observations, determine what kind of image this is. This isn't just trivia — it shapes how you generate the prompt:

- **AI-generated (likely)** — Consistent rendering style throughout, typical AI artifacts, specific aesthetic patterns associated with particular models. Note which model or style family it resembles (Midjourney cinematic, SDXL realistic, Flux detail, DALL·E illustration, etc.).
- **Real photograph** — Natural light falloff, lens characteristics, sensor noise, imperfect focus transitions. When converting to a prompt, you're creating a description that an AI could use to generate something similar, not an exact replica.
- **Digital art / illustration** — Brush strokes, layer blending, stylization choices, line art, cel shading. Identify the specific art style so the prompt captures what makes it distinctive.
- **Screenshot / UI / graphic design** — Layout, typography, UI elements. For these, describe the design system rather than trying to generate an AI image (explain this to the user).

Share your assessment with the user briefly. It builds trust and helps them understand the result.

### Step 3: Determine the output format

Ask yourself what the user needs based on context:

- Did they mention a specific platform (Midjourney, SD, DALL·E, etc.)? → Use that format
- Did the image look AI-generated in a specific model's style? → Prioritize that model's format, but offer alternatives
- Is the user speaking a non-English language? → Write prompts in English (the standard for AI generation) but wrap analysis and explanations in their language
- Did they upload a real photo and want to "recreate" it? → Midjourney or Flux format is usually best — they handle photorealistic well
- Are they a power user who seems technical? → Include advanced parameters (--stylize, --chaos, weight syntax, LoRA mentions)

If unsure, default to Midjourney format plus one alternative. Read `references/prompt-styles.md` for detailed per-platform conventions and parameters.

### Step 4: Generate the prompt

This is the core of the skill. A great prompt isn't just a list of what you see — it captures the **essence and feeling** that makes the image work. More importantly, it should give the user something they couldn't have written themselves in 30 seconds.

**Principles for high-quality prompts:**

1. **Lead with the most important thing.** The subject or the dominant impression should be first. Midjourney weights earlier words more heavily.

2. **Be specific, not wordy.** "A golden retriever puppy sleeping on a worn leather armchair beside a crackling fireplace" beats "a dog, sitting, there is a chair and a fireplace, warm feeling, cozy."

3. **Name the style explicitly.** Don't say "artistic" — say "1950s Kodachrome photography" or "Studio Trigger anime key visual" or "Rembrandt chiaroscuro portrait". Concrete style references give the model a precise target.

4. **Include atmosphere and mood words.** These are often what separate a generic prompt from a striking one: "melancholic", "serene", "electric", "nostalgic", "foreboding", "dreamlike".

5. **Add technical quality boosters where appropriate.** For photorealistic images: "8K", "award-winning photography", "sharp focus", "intricate details". For illustrations: "clean line art", "vibrant colors", "highly detailed".

6. **Always generate creative variants, not just platform translations.** This is critical — don't just convert the same prompt between Midjourney and SD. Offer genuinely different creative interpretations of the same image. For example: for a landscape photo, offer "Documentary realism", "Studio Ghibli animated version", and "Minimalist poster style" — each a distinct creative direction, not just the same words in different syntax. Label each with what's different about it so the user understands the creative choice they're making.

7. **Deliver at least one unexpected insight.** Look for something in the image the user might not have consciously noticed but that makes it special — the way fog softens the treeline, the accidental color harmony between a character's shirt and the background, the specific year a film stock was discontinued. This is what separates an "OK" output from a truly insightful one.

**Platform-specific notes:**

| Platform | Prompt Style | Key Parameters |
|----------|-------------|----------------|
| Midjourney | Comma-separated keywords, cinematic flow | `--ar`, `--style raw`, `--stylize`, `--chaos`, `--sref`, `--cref` |
| Stable Diffusion | Tag-based, weight syntax `(term:1.3)` | Negative prompt, sampler, steps, CFG scale |
| DALL·E 3 | Natural language paragraph | No parameters — quality comes from description alone |
| Flux | Similar to MJ, keyword-rich | Guidance scale, aspect ratio |
| ComfyUI | Workflow-aware descriptions | Node-compatible parameter hints |

For detailed conventions per platform, read `references/prompt-styles.md`.

### Step 5: Present the result

Default output structure (adapt to user's needs):

```
## Visual Analysis
[Key observations — not a checklist dump, but the 4-6 most important findings that shaped the prompt]

## 🔍 Source Assessment
[One sentence with reasoning]

## 🎨 Creative Directions

### [Direction 1 name, e.g., "Accurate Recreation" or "Midjourney Style"]
[Primary prompt — platform-optimized, creative, specific]

### [Direction 2 name, e.g., "Anime Reinterpretation" or "Flux Alternative"]
[Genuinely different creative take, not just syntax translation]

### [Direction 3 name, e.g., "Minimalist Poster" or "DALL·E Version"]
[Third distinct direction if the image supports it]

## 💡 Pro Tips
[1-2 non-obvious, actionable things the user can tweak — parameter changes, style mixing, what to avoid]
```

**Creative direction naming:** Don't label directions by platform name alone ("MJ version" / "SD version"). Name them by the creative intent — "Photorealistic documentary", "Synthwave reinterpretation", "Watercolor children's book". Then mention the platform in the prompt itself. This helps users understand the creative choice, not just the technical format.

**When to skip structure:** If the user's request is clearly casual ("what's the prompt for this?"), compress into a concise response. But always include at minimum: one high-quality prompt + one creative alternative + one pro tip.

---

## Quality checklist

Before presenting the final output, be honest with yourself:

- [ ] **Creative depth test:** Would a professional prompt engineer be happy to receive this, or would they say "I could have written this myself"?
- [ ] **Specificity test:** Every style reference is concrete and searchable (a named artist, movement, film stock, or technique — not "beautiful", "artistic", "stunning")
- [ ] **Surprise test:** There's at least one insight the user likely didn't notice themselves about the image
- [ ] **Variety test:** The creative directions are genuinely different from each other, not the same prompt reformatted for different platforms
- [ ] **Platform fit:** The format matches the platform (commas for MJ, tags with weights for SD, natural paragraph for DALL·E)
- [ ] **Actionability test:** The user can copy-paste the prompt and get a good result on first try — parameters, aspect ratio, and negative prompts are all included
- [ ] **Honesty:** If you're guessing about something, you said "likely" or "appears to be"

---

## Reference files

- `references/prompt-styles.md` — Detailed per-platform prompt conventions, parameters, and up-to-date best practices for Midjourney, Stable Diffusion, DALL·E, Flux, and ComfyUI
- `references/visual-analysis-guide.md` — Systematic image analysis methodology: style taxonomy, composition patterns, lighting terminology, color theory, and AI artifact identification
