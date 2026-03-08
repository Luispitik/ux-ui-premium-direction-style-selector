# Visual Direction Specifications

Each direction is a complete visual identity. All demos share the same content structure (nav, hero, storytelling, stats, services, CTA, footer) but express it through radically different aesthetics.

## Table of Contents
- [A — Editorial Serif](#a--editorial-serif)
- [B — Swiss Minimal](#b--swiss-minimal)
- [C — Luxury Dark Warm](#c--luxury-dark-warm)
- [D — Corporate Bold](#d--corporate-bold)
- [E — Understated Elegance (Kinfolk)](#e--understated-elegance-kinfolk)

---

## A — Editorial Serif

**Reference**: The Economist, Foreign Affairs, Monocle
**Mood**: Intellectual authority, printed-page sophistication

### Palette
| Role | Color | Hex |
|------|-------|-----|
| Background | Cream | `#FAFAF5` |
| Text | Navy | `#1A1F2E` |
| Accent | Gold | `#B8860B` |
| Secondary text | Muted navy | `#1A1F2E` at 60% opacity |
| Borders/Rules | Light gold | `#B8860B` at 20% opacity |

### Typography
| Role | Font | Weights | CSS Variable |
|------|------|---------|-------------|
| Display (headings) | Playfair Display | 400, 500, 600, 700 | `--font-playfair` |
| Body | Source Serif 4 | 300, 400, 500, 600 | `--font-source-serif` |

- Headlines: Playfair Display, 700, clamp(2.5rem, 5vw, 3.5rem), tracking-tight
- Body text: Source Serif 4, 400, text-lg, leading-relaxed
- Labels/caps: Source Serif 4, 500, uppercase, tracking-widest, text-xs

### Layout
- Max width: `max-w-5xl` (1024px)
- Padding: `px-6`
- Nav: Flex, brand left (Playfair italic "Luis Salgado"), links right
- Hero: Large serif headline + gold underline ornament (4px wide, 80px) + body paragraph
- Storytelling: 3 paragraphs, narrow column (~680px), editorial tone
- Stats: 3-column grid, each with gold left border (3px), large number + label
- Services: Numbered list (01/ 02/ 03/), gold number, title + description
- CTA: Centered question headline + gold-bordered button
- Footer: Simple, centered, back link to /demo

### Section Pattern
```
Nav (white bg, no border)
Hero (cream bg, large serif headline, gold accent line)
── thin gold rule ──
Storytelling (cream bg, narrow body text)
── thin gold rule ──
Stats (cream bg, 3-col with gold left borders)
── thin gold rule ──
Services (cream bg, numbered 01/ 02/ 03/)
CTA (cream bg, centered, gold outline button)
Footer (cream bg, minimal)
```

### Distinguishing Details
- Gold horizontal rule ornaments between sections
- Italic serif for brand name
- No background color changes between sections — pure cream throughout
- Server Component (no `'use client'`) — no hover effects needed

---

## B — Swiss Minimal

**Reference**: Dieter Rams, Braun, Swiss International Style
**Mood**: Radical reduction, functional clarity, nothing decorative

### Palette
| Role | Color | Hex |
|------|-------|-----|
| Background | White | `#FFFFFF` |
| Text | Black | `#0A0A0A` |
| Accent (CTAs only) | Red | `#D42B2B` |
| Secondary text | Black at 60% | `#0A0A0A` at 60% opacity |
| Muted text | Black at 50% | `#0A0A0A` at 50% opacity |
| Borders | Light gray | `#E5E5E5` |

### Typography
| Role | Font | Weights | CSS Variable |
|------|------|---------|-------------|
| Display (headings, numbers) | Space Grotesk | 500, 600, 700 | `--font-space-grotesk` |
| Body | Inter | 400, 500 | `--font-inter` |

- Headlines: Space Grotesk, 700, clamp(2.5rem, 6vw, 5rem), leading-[1.05], tracking-tight
- Body text: Inter, 400, text-base to text-lg, leading-relaxed
- Labels: Inter, 400, text-sm, uppercase, tracking-widest, 50% opacity
- Numbers: Space Grotesk, 700, clamp(3rem, 5vw, 4rem)

### Layout
- Max width: `max-w-[1200px]` (1200px)
- Padding: `px-6 md:px-10`
- Nav: Fixed top, white/95 backdrop-blur, border-b. Brand: "LS" in Space Grotesk bold. Links right.
- Hero: Massive headline (5rem desktop), short subtitle, red text link CTA with arrow →
- Storytelling: Single paragraph, narrow (600px), relaxed leading
- Stats: 3-column, divided by vertical borders (md:border-r), large numbers
- Services: Numbered (01/ 02/ 03/), mono-style number prefix, title + description, separated by border-b
- CTA: Full-width red (#D42B2B) background band. White text headline + button (white bg, red text)
- Footer: Border-top, flex row, copyright left, back link right

### Section Pattern
```
Nav (fixed, white, border-b)
Hero (white, massive headline, red link CTA)
── gray rule ──
Storytelling (white, single paragraph)
── gray rule ──
Stats (white, 3-col with vertical dividers)
── gray rule ──
Services (white, numbered list with border-b)
CTA (RED full-width band, white text/button)
Footer (white, border-t, minimal)
```

### Distinguishing Details
- Red appears ONLY in CTAs — nowhere else. Maximum restraint.
- Gray horizontal rules (`border-[#E5E5E5]`) divide every section
- Vertical borders between stat columns instead of cards
- Monospace-style numbering (01/ 02/ 03/) for services
- Server Component — no interactive effects

---

## C — Luxury Dark Warm

**Reference**: Aesop, Byredo, high-end hospitality
**Mood**: Intimate, warm darkness, quiet confidence

### Palette
| Role | Color | Hex |
|------|-------|-----|
| Background | Charcoal | `#171614` |
| Text | Cream | `#F0EBE1` |
| Accent | Copper | `#C4956A` |
| Secondary text | Stone | `#8A8174` |
| Card bg | Dark raised | `#1E1D1A` |
| Borders | Copper at 30% | `rgba(196,149,106,0.3)` |

### Typography
| Role | Font | Weights | CSS Variable |
|------|------|---------|-------------|
| Display (headings) | Cormorant Garamond | 300, 400, 500, 600 | `--font-cormorant` |
| Body | Outfit | 300, 400, 500 | `--font-outfit` |

- Headlines: Cormorant Garamond, 300-400, clamp(2.5rem, 5vw, 4rem), tracking-wide
- Body text: Outfit, 300, text-base to text-lg, leading-relaxed
- Labels: Outfit, 400-500, text-xs, uppercase, tracking-[0.2em]
- Nav links: Outfit, 300, text-sm, letter-spacing 0.15em

### Layout
- Max width: varies (px-8 md:px-16 for full-bleed feel, max-w-4xl for content)
- Nav: Fixed, transparent charcoal (92% opacity) + backdrop-blur. Brand as styled text. Links with copper hover.
- Hero: Full viewport height (`min-h-screen`), centered vertically. Thin copper line ornament above headline. Scroll indicator at bottom.
- Storytelling: 4 short paragraphs, narrow column (max-w-2xl), intimate tone
- Stats: Dark cards (`#1E1D1A`) in 3-column grid, copper top border (2px), large light numbers + stone labels
- Services: Copper-bordered cards (1px border, 30% opacity). Hover brightens border to full copper. Title + description.
- CTA: Copper background section. Dark text. Simple message + button.
- Footer: Charcoal, copper top border, minimal

### Section Pattern
```
Nav (fixed, charcoal 92%, backdrop-blur)
Hero (full-height, centered, copper line ornament, scroll indicator)
Storytelling (charcoal, narrow, 4 paragraphs)
Stats (charcoal, dark cards with copper top borders)
Services (charcoal, copper-bordered cards with hover)
CTA (COPPER full-width band, dark text)
Footer (charcoal, copper rule, minimal)
```

### Distinguishing Details
- `'use client'` required — hover effects on service cards (onMouseEnter/onMouseLeave)
- Full-height hero with scroll indicator animation
- Copper line ornament (`w-16 h-[1px]`) above hero headline
- Light font weights throughout (300) for airy elegance
- No sharp edges — everything breathes with generous spacing

---

## D — Corporate Bold

**Reference**: Accenture, McKinsey Digital, enterprise SaaS
**Mood**: Confidence, authority, structured professionalism

### Palette
| Role | Color | Hex |
|------|-------|-----|
| Background (light sections) | White | `#FFFFFF` |
| Background (dark sections) | Navy | `#0F1923` |
| Text (on white) | Navy | `#0F1923` |
| Text (on navy) | White | `#FFFFFF` |
| Accent | Purple | `#5B21B6` |
| Secondary text | Gray | `#0F1923` at 60% opacity |
| Card bg | Light gray | `#F1F5F9` |
| Borders | Slate | `#E2E8F0` |

### Typography
| Role | Font | Weights | CSS Variable |
|------|------|---------|-------------|
| All text | Plus Jakarta Sans | 400, 500, 600, 700, 800 | className directly |

- Headlines: Plus Jakarta Sans, 800, clamp(2.5rem, 5vw, 3.5rem), tracking-tight
- Body text: Plus Jakarta Sans, 400, text-base to text-lg
- Buttons: Plus Jakarta Sans, 600-700, uppercase, tracking-wider, text-sm
- Labels: Plus Jakarta Sans, 600, uppercase, tracking-widest

### Layout
- Max width: `max-w-[1100px]`
- Padding: `px-6`
- Nav: Fixed, white bg, shadow on scroll (useState + useEffect). Brand bold left, links + purple CTA button right.
- Hero: Bold headline + two CTAs side-by-side (purple filled + outline). White bg.
- Stats: Full-width NAVY band. 4 metrics in row (include aspirational stat like "95%*" with asterisk footnote). White text on navy.
- Services: 3-phase method columns on light gray cards (`#F1F5F9`). Phase number badge (purple bg, white text). White bg section.
- Why-different: Navy bg section. 3 bold points with purple left borders.
- CTA: Purple (`#5B21B6`) full-width band. White text. Large button.
- Footer: Navy bg, white text, minimal

### Section Pattern
```
Nav (fixed, white, shadow-on-scroll)
Hero (white bg, bold headline, two CTAs)
Stats (NAVY full-width band, 4 metrics)
Services/Method (white bg, 3 gray cards)
Why-Different (NAVY bg, purple left-border points)
CTA (PURPLE full-width band)
Footer (navy bg, minimal)
```

### Distinguishing Details
- `'use client'` required — useState + useEffect for nav scroll shadow
- Alternating white/navy sections create strong rhythm
- Two CTA buttons in hero (filled + outline)
- Aspirational metric with asterisk footnote
- Single font family (Plus Jakarta Sans) — variety through weight only (400-800)
- Geometric confidence: straight lines, sharp corners, bold weights

---

## E — Understated Elegance (Kinfolk)

**Reference**: Kinfolk magazine, Cereal, Aesop retail
**Mood**: Quiet sophistication, editorial calm, deliberate whitespace

### Palette
| Role | Color | Hex |
|------|-------|-----|
| Background | Bone | `#F5F2ED` |
| Text | Charcoal | `#2C2C2C` |
| Accent | Olive | `#6B705C` |
| Secondary text | Warm gray | `#A8A29E` |
| Borders | Warm gray at 40% | `#A8A29E` at 40% opacity |

### Typography
| Role | Font | Weights | CSS Variable |
|------|------|---------|-------------|
| Display (headings) | Libre Baskerville | 400, 700 | `--font-libre` |
| Body | Karla | 300, 400, 500 | `--font-karla` |

- Headlines: Libre Baskerville, 400 (regular, not bold), text-3xl to text-4xl, leading-snug
- Body text: Karla, 300-400, text-base, leading-relaxed
- Labels: Karla, 400, text-xs, uppercase, tracking-[0.15em]
- Nav links: Karla, 300, text-sm, tracking-wide

### Layout
- Max width: content is very narrow (`max-w-xl` = 576px for body, `max-w-2xl` for sections)
- Padding: `px-6 md:px-12 lg:px-20`
- Nav: Not fixed. Generous top padding (pt-10). Brand as text, olive dot (●) as active indicator. Links right.
- Hero: Centered text, generous vertical space (pt-32 pb-20). Regular weight serif headline (NOT bold). Subtitle in warm gray.
- Storytelling: 3 paragraphs in very narrow column (max-w-xl, ~576px). Light font weight. Generous line-height.
- Stats: 3-column, subtle warm-gray top border per stat. Small numbers (text-3xl, not massive). Olive accent on labels.
- Services: Simple list, no cards, no borders between items. Just title + description. Olive hover on title.
- CTA: Bone bg continues. Quiet question as headline. Olive outline button (1px border). No color change.
- Footer: Top border (warm gray), copyright + back link

### Section Pattern
```
Nav (not fixed, bone bg, generous padding)
Hero (bone bg, centered, regular-weight serif, lots of air)
── warm gray rule ──
Storytelling (bone bg, very narrow column, 3 paragraphs)
── warm gray rule ──
Stats (bone bg, subtle top borders, small numbers)
── warm gray rule ──
Services (bone bg, no cards, hover title color)
── warm gray rule ──
CTA (bone bg, quiet question, olive outline button)
Footer (bone bg, warm gray rule, minimal)
```

### Distinguishing Details
- `'use client'` required — hover effects on service titles
- Barely-there nav with olive dot active indicator
- Regular-weight headings (400, not bold) — intentional restraint
- Narrowest content column of all directions (~576px body)
- No section background changes — bone throughout
- Warm gray rules between every section
- Everything whispers — nothing shouts

---

## Copy Tone Guidelines Per Direction

| Direction | Tone | Sentence Style | Example Opening |
|-----------|------|---------------|----------------|
| Editorial | Authoritative, measured | Long, structured, with subordinate clauses | "In an era where every consultancy promises transformation..." |
| Minimal | Direct, stripped | Short, declarative, no ornament | "Your team doesn't need another AI course." |
| Luxury | Intimate, refined | Flowing, personal, sensory language | "There is a particular kind of clarity that comes from..." |
| Corporate | Confident, structured | Active voice, data-driven, results-oriented | "Leading companies don't wait for AI readiness." |
| Kinfolk | Thoughtful, quiet | Conversational, questioning, first-person | "I studied psychology, not engineering." |

## Common Section Structure (All Directions)

Every demo page MUST include these sections in order:
1. **Nav** — Brand + navigation links + optional CTA
2. **Hero** — Headline + subtitle/description + primary CTA
3. **Storytelling** — Personal narrative (founder story, unique angle)
4. **Stats** — 3-4 key numbers with labels
5. **Services** — 3-4 offerings with descriptions
6. **CTA** — Final call to action (booking, contact)
7. **Footer** — Copyright + back link to `/demo`

## Technical Requirements

- Each page: self-contained, only imports `next/link` and `next/font/google`
- Colors via inline `style` attributes, NOT Tailwind theme (demos must not depend on project config)
- Fonts via `next/font/google` with `variable` prop and CSS variable usage
- Pages with event handlers (onMouseEnter, useState, useEffect): MUST have `'use client'`
- Pages with `'use client'`: MUST NOT export `metadata`
- Server Component pages: CAN export `metadata`
- All pages: responsive (mobile + desktop via Tailwind breakpoints)
- Back link to `/demo` in every footer
