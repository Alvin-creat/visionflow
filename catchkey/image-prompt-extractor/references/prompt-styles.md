# Prompt Styles Reference

Comprehensive per-platform prompt conventions. Reference this when the user specifies a platform or when you need detailed parameter knowledge.

---

## Midjourney (v6 / v7)

### Prompt structure
Comma-separated descriptive phrases. Earlier words carry more weight. Flow from subject → environment → style → lighting → technical quality → parameters.

```
[primary subject], [context/environment], [art style/medium], [lighting], [mood], [camera/technical], [quality boosters] --[parameters]
```

### Key parameters

| Parameter | Range | Usage |
|-----------|-------|-------|
| `--ar <w>:<h>` | e.g., 16:9, 1:1, 9:16, 3:2 | Aspect ratio. Match the source image. |
| `--style raw` | on/off | Reduces Midjourney's default "beautification". Use for realistic/photographic results. |
| `--stylize <n>` / `--s <n>` | 0–1000 (default 100) | Higher = more artistic interpretation. 0 = literal, 250 = balanced, 1000 = maximum artistic. |
| `--chaos <n>` / `--c <n>` | 0–100 | Variety across the 4-image grid. 0 = consistent, 100 = wildly different. |
| `--sref <url>` | URL | Style reference — copy the aesthetic of another image. |
| `--cref <url>` | URL | Character reference — preserve character consistency. |
| `--cw <n>` | 0–100 | Character weight for `--cref`. 100 = full character, 0 = pose only. |
| `--no <term>` | text | Negative prompting — what to exclude. |
| `--seed <n>` | integer | Reproducibility. Same seed + same prompt = similar result. |
| `--p` | — | Personalization (requires prior setup). |
| `--weird <n>` | 0–3000 | Experimental: introduces unconventional elements. |

### Style families that work well in Midjourney

**Photographic:** `35mm Kodak Portra 400`, `Hasselblad medium format`, `Helmut Newton fashion`, `Annie Leibovitz portrait`, `National Geographic documentary`, `aerial drone photography`, `macro 100mm lens`

**Cinematic:** `cinematic lighting`, `Wes Anderson symmetry`, `Christopher Nolan scope`, `Blade Runner 2049 aesthetic`, `Wong Kar-wai color grade`, `anamorphic lens flare`, `IMAX ratio`

**Illustration:** `Studio Ghibli cel animation`, `Loish character art`, `James Jean surrealism`, `Alphonse Mucha art nouveau`, `Moebius ligne claire`, `Syd Mead futurism`, `Ashley Wood painterly`

**3D / Render:** `Unreal Engine 5`, `Octane render`, `Blender cycles`, `ZBrush sculpt`, `clay render`, `wireframe`, `isometric 3D`, `low poly`, `Pixar-style animation`

### Examples

**Photorealistic portrait:**
```
young woman with silver hair and piercing blue eyes, soft window light from the left, shallow depth of field, dust motes floating in sunbeams, vintage cream linen dress, 85mm f/1.4 portrait lens, Hasselblad color science, editorial fashion photography --ar 4:5 --style raw --s 50
```

**Anime illustration:**
```
cyberpunk cityscape at twilight, neon signs reflecting in rain puddles, lone figure in a transparent umbrella, flying cars in the distance, Makoto Shinkai lighting, detailed background illustrations, anime key visual --ar 16:9 --niji 6
```

**Product / object:**
```
minimalist ceramic teapot, matte white glaze with subtle crackle texture, zen composition on a dark wooden board, soft diffused studio lighting, condensation droplets, product photography, Apple-style clean aesthetic --ar 1:1 --style raw --s 0
```

---

## Stable Diffusion (SDXL / SD3 / SD3.5)

### Prompt structure
Tag-based system. Use comma-separated tags and phrases. Weight syntax with parentheses.

```
masterpiece, best quality, [score tags], [subject], [style], [composition], [lighting], [details]
```

### Weight syntax
- `(keyword)` — increase weight by 1.1x
- `((keyword))` — increase weight by 1.21x (1.1²)
- `(keyword:1.3)` — explicit weight multiplier
- `[keyword]` — decrease weight by 0.9x

### Score tags (commonly used)
`masterpiece`, `best quality`, `high quality`, `absurdres`, `intricate details`, `sharp focus`, `professional`

### Negative prompts
Common negative prompt template:
```
worst quality, low quality, normal quality, bad anatomy, bad hands, extra fingers, missing fingers, blurry, jpeg artifacts, signature, watermark, text, logo, username, deformed, ugly, mutated, disfigured, lowres, bad proportions, extra limbs, cloned face, gross proportions, malformed limbs, missing arms, missing legs, fused fingers, too many fingers, long neck
```

### Style tags (by category)
**Realistic:** `photorealistic`, `hyperrealistic`, `RAW photo`, `8k uhd`, `dslr`, `soft lighting`, `film grain`

**Anime:** `anime screencap`, `anime coloring`, `flat color`, `cel shading`, `lineart`, `manga style`

**Artistic:** `digital painting`, `oil painting`, `watercolor`, `charcoal sketch`, `concept art`, `matte painting`

**3D:** `3d render`, `octane render`, `unreal engine 5`, `ray tracing`, `subsurface scattering`

### SDXL-specific notes
- Handles longer prompts better than SD 1.5
- Natural language descriptions work better alongside tags
- Resolution: 1024x1024 native, can go higher with good results

### SD3 / SD3.5 notes
- Much better at natural language understanding
- Less dependent on tag formatting
- Handles text-in-image better than previous versions
- Resolution: 1024x1024 to 1536x1536

---

## DALL·E 3 (OpenAI)

### Prompt structure
Natural language paragraph. Think of it as describing a scene to a human artist. No special syntax needed.

DALL·E 3 works best with:
- Complete sentences describing the scene holistically
- Emotional/atmospheric language
- Specific artistic references and styles
- Clear compositional intent

### What DALL·E 3 handles well
- Complex scenes with multiple interacting elements
- Text in images (better than most other models)
- Following precise layout instructions
- Understanding abstract concepts expressed in natural language

### What it struggles with
- Extreme photorealism (SD/Flux are better)
- Consistent character across multiple generations
- Very specific technical camera parameters (though it tries)

### Example
```
A cozy attic reading room bathed in warm evening light. A large arched window fills the left wall, showing a winter snowscape outside. An overstuffed burgundy armchair sits beside a tower of worn hardcover books. A brass reading lamp casts a golden pool of light across an open book. A sleeping tabby cat curls on a knitted throw blanket. Dust motes dance in the slanted sunbeams. The walls are lined with dark wooden bookshelves. Digital painting in the style of a cozy Studio Ghibli interior, with rich textures and a nostalgic atmosphere.
```

---

## Flux (Black Forest Labs)

### Prompt structure
Similar to Midjourney — keyword-heavy, comma-separated phrases. Flux responds well to detailed, descriptive prompting.

### Key characteristics
- Excellent photorealism and detail
- Good anatomy (hands especially — better than most)
- Handles text reasonably well
- Native resolution: multiple, including high-res
- Guidance scale: typically 3.5–7.0 (lower than SD)

### Best practices
- Be specific about lighting and materials
- Use photographic terminology for realistic results
- Style references work well (artist names, film stocks, etc.)
- Less need for quality booster tags than SD
- Aspect ratios: supports many including ultra-wide

### Example
```
A middle-aged Japanese potter at his wheel in a sunlit workshop, hands covered in wet clay, intense concentration on his face, shafts of light through dusty windows, shelves of unfinished ceramics behind him, documentary photography style, Fujifilm Provia color profile, natural light, shallow depth of field, 35mm lens
```

---

## ComfyUI

### Prompting approach
ComfyUI is a node-based UI, not a model itself. The model being used determines the prompt format. Common models used in ComfyUI:

- **SDXL / SD3** — Use SD conventions above
- **Flux** — Use Flux conventions above
- **SD 1.5** — Use tag-heavy SD conventions, shorter prompts
- **Custom merges** — Generally follow SD conventions

### Workflow-level hints (useful for power users)
- For inpainting: describe the specific area to modify
- For img2img: mention the degree of transformation desired
- For ControlNet: describe the structural elements being preserved (pose, depth, edges)
- For IP-Adapter: describe the style transfer goal

---

## Quick format selector

| User says... | Use format |
|-------------|------------|
| "Midjourney", "MJ", "niji" | Midjourney comma-separated + parameters |
| "Stable Diffusion", "SD", "SDXL", "A1111", "Forge" | SD tags + weights + negative prompt |
| "DALL·E", "ChatGPT image", "OpenAI" | Natural language paragraph |
| "Flux" | MJ-style keywords, fewer boosters, focus on detail |
| "ComfyUI", "Comfy" | Match to the model they're likely using |
| Doesn't specify | Default to Midjourney + one alternative |

---

## Universal quality boosters (use judiciously)

For photorealism: `8K`, `ultra high resolution`, `award-winning photography`, `sharp focus`, `intricate details`

For illustration: `highly detailed`, `vibrant colors`, `clean linework`, `professional illustration`

For 3D: `ray traced`, `global illumination`, `ambient occlusion`, `subsurface scattering`, `8K render`

**Important:** Don't pile on boosters mindlessly. A prompt with 10 quality tags reads as amateur — the model (and the user) can tell. Pick 2-3 that genuinely enhance the specific image.
