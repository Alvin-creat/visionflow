# Visual Analysis Guide

A systematic framework for observing and describing images. Use this when you need help identifying styles, composition patterns, or AI artifacts.

---

## 1. Style Taxonomy

### Photography styles

| Style | Visual markers | How to describe |
|-------|---------------|-----------------|
| Portrait photography | Shallow DOF, eye contact, posed | "[focal length] portrait lens, [emotion] expression" |
| Street photography | Candid, natural light, urban | "candid street photography, [city] streets, natural light" |
| Documentary | Unposed, available light, storytelling | "documentary style, [subject] in natural habitat" |
| Fashion editorial | Stylized posing, dramatic lighting | "editorial fashion, [brand/genre] aesthetic, studio lighting" |
| Macro | Extreme close-up, tiny details | "macro photography, [distance]mm lens, extreme detail" |
| Aerial / drone | Top-down, landscape scale | "aerial drone photography, bird's-eye view" |
| Astrophotography | Night sky, stars, long exposure | "astrophotography, long exposure, Milky Way" |
| Food photography | Styled plating, side light | "food photography, culinary styling, natural window light" |
| Architectural | Straight lines, perspective control | "architectural photography, [style] building, wide angle" |

### Art movements as style references
Naming an art movement gives the model a precise aesthetic target. Here are the most useful ones for prompting:

| Movement | Visual character | Good for |
|----------|-----------------|----------|
| Impressionism | Visible brushstrokes, light focus | Landscapes, outdoor scenes |
| Art Nouveau | Flowing organic lines, decorative | Posters, decorative illustrations |
| Art Deco | Geometric, luxurious, symmetrical | Architecture, fashion, luxury |
| Surrealism | Dreamlike, impossible juxtapositions | Conceptual, artistic images |
| Bauhaus | Geometric, functional, primary colors | Minimalist, modern design |
| Pop Art | Bold colors, Ben-Day dots, commercial | Fun, colorful, graphic |
| Ukiyo-e | Flat colors, outlines, Japanese | Japanese aesthetic, landscapes |
| Renaissance | Chiaroscuro, pyramidal composition | Classical portraits, dramatic scenes |
| Baroque | Dramatic lighting, movement, richness | Dramatic, emotional scenes |
| Rococo | Pastels, ornate, playful | Delicate, romantic images |
| Romanticism | Dramatic nature, emotion | Landscapes, emotional scenes |
| Pre-Raphaelite | Detailed, medieval, vivid colors | Fantasy, romantic portraits |
| Cubism | Fragmented perspective, geometric | Abstract, conceptual |
| Minimalism | Less is more, clean space | Modern, architectural |
| Vaporwave | Neon, glitch, retro digital | Retro-futuristic, nostalgic |
| Brutalism | Raw concrete, massive forms | Architectural, dystopian |

### Illustration styles

| Style | Key identifiers | Prompt keywords |
|-------|----------------|-----------------|
| Anime (general) | Large eyes, cel shading, speed lines | `anime style, cel shading` |
| 90s anime | Grainy, hand-painted cels | `90s anime cel, grainy, hand-painted background` |
| Studio Ghibli | Soft backgrounds, delicate characters | `Studio Ghibli, Miyazaki, watercolor background` |
| Makoto Shinkai | Hyper-detailed skies, lens flares | `Makoto Shinkai, photorealistic background, god rays` |
| Manga | Black & white, screentones, panels | `manga style, screentone, crosshatching` |
| Manhwa/Webtoon | Full color, vertical scroll, polished | `webtoon style, digital coloring, clean lines` |
| Comic book (Western) | Bold outlines, halftone dots, action | `comic book style, halftone, dynamic posing` |
| Pixel art | Visible pixels, limited palette | `pixel art, 16-bit, [N] colors, dithering` |
| Vector art | Flat colors, clean curves | `vector illustration, flat design, gradient mesh` |
| Children's book | Whimsical, warm, storybook | `children's book illustration, watercolor, whimsical` |
| Scientific illustration | Precise, labeled, educational | `scientific illustration, botanical, anatomical` |
| Concept art | Loose, atmospheric, exploratory | `concept art, speedpaint, visual development` |
| Storyboard | Rough, sequential, directional arrows | `storyboard frames, rough sketch, camera direction` |
| Caricature | Exaggerated features, humorous | `caricature, exaggerated proportions, humorous` |

### 3D / Render styles

| Style | Visual characteristics | Prompt keywords |
|-------|----------------------|-----------------|
| Photoreal render | Indistinguishable from photo | `photorealistic render, path traced, 8K` |
| Pixar / Disney 3D | Rounded forms, expressive, subsurface | `Pixar style, Disney animation, 3D animated` |
| Low poly | Faceted surfaces, minimalist | `low poly, flat shading, stylized 3D` |
| Isometric | 45° angle, game-like | `isometric view, diorama, tilt-shift` |
| Clay render | Matte, uniform material, soft | `clay render, ambient occlusion, sculpt preview` |
| Wireframe | Lines showing mesh topology | `wireframe render, topology lines, blueprint` |
| Voxel | Blocky, Minecraft-like | `voxel art, blocky 3D, cubic style` |
| Product viz | Clean, studio lighting, floating | `product visualization, studio lighting, hero shot` |

---

## 2. Composition Patterns

### Classic composition types
Knowing these helps you describe the image precisely:

- **Rule of thirds** — Subject placed at intersection points
- **Centered / Symmetrical** — Subject dead center, mirror-like balance (Wes Anderson style)
- **Golden ratio / spiral** — Natural flow leading to focal point
- **Leading lines** — Roads, rivers, architecture guiding the eye
- **Frame within a frame** — Doorway, window, arch framing the subject
- **Diagonal / Dutch angle** — Tilted camera for tension or dynamism
- **Negative space** — Subject occupies small portion, lots of breathing room
- **Fill the frame** — Subject dominates, no empty space
- **Bird's-eye / Top-down** — Looking straight down
- **Worm's-eye** — Looking straight up from ground level
- **Over-the-shoulder** — Viewer behind someone, seeing what they see
- **POV / First-person** — Camera is the character's eyes

### Aspect ratio as compositional intent
- **1:1** — Square, balanced, often for social media or product shots
- **3:2 / 2:3** — Classic 35mm photo ratio (most natural to the eye)
- **4:5 / 5:4** — Portrait orientation, common in fashion and Instagram
- **16:9** — Cinematic widescreen, landscape, storytelling
- **9:16** — Vertical video, phone-native, stories/reels
- **21:9** — Ultra-wide cinema, epic landscapes, panoramic
- **3:1 / 4:1** — Extreme panorama, establishing shots

---

## 3. Lighting Terminology

### Light source descriptions

| Term | What it means | Use when... |
|------|--------------|-------------|
| Golden hour | Warm, low-angle sunlight just after sunrise/before sunset | The image has warm, golden tones and long shadows |
| Blue hour | Cool, diffused light just before sunrise/after sunset | Deep blue tones, city lights turning on |
| Overcast / Diffused | Cloud-filtered, shadowless | Soft light with no distinct shadow direction |
| Harsh midday | Strong overhead sun, deep shadows | High contrast, distinct shadow under chin/nose |
| Studio / Three-point | Key + fill + rim artificial light | Clean, controlled lighting with subtle rim separation |
| Neon / Cinematic | Colored artificial light sources | Pink/blue/teal gels, Blade Runner aesthetic |
| Candlelight / Warm | Single warm point source | Intimate, flickering, orange tones |
| Moody / Low-key | Mostly dark with selective illumination | Drama, mystery, chiaroscuro |
| High-key | Bright, minimal shadows | Clean, airy, commercial look |
| Backlit / Rim light | Light from behind the subject | Silhouette or hair/shoulder glow edge |
| Dappled light | Light filtered through leaves/trees | Outdoor summer, dynamic shadow patterns |
| Volumetric / God rays | Visible light beams in atmosphere | Dust, fog, or smoke making light rays visible |
| Bioluminescent | Living light sources | Fantasy, underwater, alien |

### Lighting direction
- **Front light** — Flattens features, can feel clinical
- **Side light** — Emphasizes texture and form, dramatic
- **Rembrandt lighting** — 45° side, triangle of light under eye
- **Top light** — Creates deep eye shadows, can feel ominous
- **Bottom light** — Unnatural, horror/thriller vibe
- **Loop lighting** — Slightly above and to the side, flattering for portraits

---

## 4. Color Theory Quick Reference

### Color harmonies to name
- **Monochromatic** — Single hue, varying saturation and brightness
- **Analogous** — Adjacent colors on the wheel (e.g., blue-teal-green)
- **Complementary** — Opposites (e.g., orange + teal, red + cyan)
- **Triadic** — Three evenly spaced (e.g., red-yellow-blue)
- **Split-complementary** — One color + two adjacent to its complement

### Mood associations (use in prompts)
- **Warm** (reds, oranges, yellows): energetic, passionate, cozy, inviting
- **Cool** (blues, teals, purples): calm, professional, melancholic, mysterious
- **Muted / Desaturated**: nostalgic, serious, vintage, somber
- **Vibrant / Saturated**: energetic, youthful, bold, pop
- **Pastel**: soft, dreamy, feminine, spring
- **Neon**: electric, cyberpunk, retro, nightlife
- **Earth tones**: natural, organic, rustic, grounded

### Common color grading styles
- **Teal & Orange** — Hollywood blockbuster look, complementary contrast
- **Bleach bypass** — Desaturated, high contrast, gritty (Saving Private Ryan)
- **Cross-processed** — Color shifts, vintage film look
- **Technicolor** — Rich, saturated, classic Hollywood musical
- **Kodachrome** — Warm reds, deep blues, iconic mid-century look
- **Fuji Pro 400H** — Soft pastels, green-tinted shadows, wedding photography
- **Kodak Portra** — Warm skin tones, soft contrast, portrait standard

---

## 5. AI Artifact Identification

### Model-specific tells

**Midjourney (v4–v6):**
- Tendency toward glossy/plastic skin texture at default settings
- Dramatic, cinematic lighting by default (v6 reduced this somewhat)
- Hands often have wrong finger count or impossible poses
- Complex backgrounds can have nonsense structures
- Signature "MJ aesthetic" — slightly dreamlike, highly polished
- Niji model: distinct anime style with detailed eyes

**Stable Diffusion (SDXL):**
- More varied output quality depending on model
- Common: inconsistent eyes (different iris sizes), melded limbs
- Backgrounds often simpler than MJ but can be more chaotic
- Hands still problematic but improving
- Realistic models: can look surprisingly photographic until you spot texture oddities
- Often has slight "plastic" or "CGI" quality to skin

**DALL·E 3:**
- Strong composition, sometimes overly perfect/balanced
- Can struggle with photorealistic texture — often looks "illustrated"
- Better than most at complex multi-object scenes
- Faces can have slight uncanny valley quality
- Often produces images that look like "good digital art" rather than photos

**Flux:**
- Very high detail and realism, can be hard to distinguish from photos
- Good anatomy overall, fewer hand issues
- Skin texture more natural than MJ or SD
- Sometimes has a slightly "rendered" quality under close inspection
- Text rendering better than most but not perfect

### General AI generation markers
- Inconsistent lighting logic (shadows in wrong directions)
- Background elements that merge or don't resolve
- Symmetry errors (earrings different, buttons mismatched)
- Fabric/patterns that don't follow 3D contours correctly
- Water reflections that don't match the scene
- Architecture with impossible structure
- Hyper-perfect symmetry in organic subjects
- Unnatural uniformity in crowd/distant figures

### When the image is NOT AI-generated
- Natural sensor noise visible at pixel level
- Lens aberrations (chromatic aberration, vignetting, barrel distortion)
- Metadata/EXIF data (if accessible)
- Human tattoo variations, natural skin imperfections
- Coincidental real-world details too specific for AI (real brand labels, readable text on posters)
- Imperfect focus falloff following real optical physics

---

## 6. The "First Impression" Checklist

Before diving into analysis details, capture your gut reaction. These often contain the most important prompt elements:

1. **First three words that come to mind** — These might be the most important prompt keywords
2. **What's the dominant emotion?** — This should shape the atmosphere/mood of the prompt
3. **If this were a movie, what genre?** — Helps zero in on the style family
4. **What's the one thing that makes this image special?** — This is what the prompt must capture

This quick gut check often produces better prompts than exhaustive technical analysis alone. The technical analysis supplies precision; the gut check supplies soul. A great prompt needs both.
