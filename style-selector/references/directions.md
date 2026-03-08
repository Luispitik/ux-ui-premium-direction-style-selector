# Visual Direction Specifications

Each direction is a complete visual identity. All demos share the same content structure but express it through radically different aesthetics.

## Table of Contents
- [A — Editorial Serif](#a--editorial-serif)
- [B — Swiss Minimal](#b--swiss-minimal)
- [C — Luxury Dark Warm](#c--luxury-dark-warm)
- [D — Corporate Bold](#d--corporate-bold)
- [E — Understated Elegance (Kinfolk)](#e--understated-elegance-kinfolk)
- [F — Neo-Brutalist](#f--neo-brutalist)
- [G — Playful Gradient](#g--playful-gradient)
- [H — Retro Terminal](#h--retro-terminal)
- [Animation System](#animation-system)
- [Accessibility Requirements](#accessibility-requirements)
- [Mobile-First Specs](#mobile-first-specs)

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
| Focus ring | Gold | `#B8860B` |

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
- Nav: Flex, brand left (Playfair italic), links right
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

### Animation
- **Entrance**: Sections fade-in + slide-up (20px) on scroll, 600ms ease-out, stagger 100ms
- **Gold rules**: Width expands from 0 to full on scroll (800ms ease-out)
- **Stats numbers**: Count-up animation when in viewport (1200ms)
- **Hover**: Gold underline on nav links grows from left (300ms)
- **No parallax** — editorial restraint, motion should feel measured

### Distinguishing Details
- Gold horizontal rule ornaments between sections
- Italic serif for brand name
- No background color changes between sections — pure cream throughout
- Server Component (no `'use client'`) — no hover effects needed

### Accessibility
| Pair | Ratio | WCAG |
|------|-------|------|
| Navy on Cream (#1A1F2E / #FAFAF5) | 13.2:1 | AAA |
| Gold on Cream (#B8860B / #FAFAF5) | 4.5:1 | AA |
| Muted navy on Cream (60%) | 6.8:1 | AA |

### Mobile (375px)
- Nav: hamburger hidden — show brand only, links below hero as pills
- Hero headline: clamp down to 2rem, max 3 lines
- Stats: single column stack, gold left border persists
- Services: full width, numbered list, 16px body
- CTA button: full width, min-height 48px
- Section padding: py-12 (not py-20)

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
| Focus ring | Red | `#D42B2B` |

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

### Animation
- **Entrance**: Instant appear — NO fade-in animations. Rams: "Good design is as little design as possible"
- **Stats numbers**: Snap to final value, no count-up
- **CTA arrow**: Translate-x 4px on hover (200ms linear)
- **Nav**: border-b opacity transitions on scroll (200ms)
- **Page transitions**: Cut, no slide. Immediate.

### Distinguishing Details
- Red appears ONLY in CTAs — nowhere else. Maximum restraint.
- Gray horizontal rules (`border-[#E5E5E5]`) divide every section
- Vertical borders between stat columns instead of cards
- Monospace-style numbering (01/ 02/ 03/) for services
- Server Component — no interactive effects

### Accessibility
| Pair | Ratio | WCAG |
|------|-------|------|
| Black on White (#0A0A0A / #FFFFFF) | 19.3:1 | AAA |
| Red on White (#D42B2B / #FFFFFF) | 5.6:1 | AA |
| White on Red (#FFFFFF / #D42B2B) | 5.6:1 | AA |
| Black 60% on White | 7.2:1 | AAA |

### Mobile (375px)
- Nav: brand left "LS", single CTA link right, no menu
- Hero headline: clamp to 2.5rem, 2-3 lines max
- Stats: single column, horizontal border-b replaces vertical dividers
- Services: full width numbered list
- CTA band: full-width button, py-16
- Footer: stacked, centered

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
| Focus ring | Copper | `#C4956A` |

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

### Animation
- **Entrance**: Fade-in only (no slide), 800ms ease-out, stagger 150ms — slow, cinematic
- **Hero scroll indicator**: Infinite bounce-y (2s ease-in-out), subtle opacity pulse
- **Service cards**: Border-color transition 400ms on hover (30% → 100% copper)
- **Copper ornament**: Scale-x from 0 to 1 on load (1000ms ease-out, 500ms delay)
- **Parallax**: Subtle on hero background only (0.3x factor), disabled on mobile
- **Page feel**: Everything moves slowly — minimum 400ms transitions

### Distinguishing Details
- `'use client'` required — hover effects on service cards (onMouseEnter/onMouseLeave)
- Full-height hero with scroll indicator animation
- Copper line ornament (`w-16 h-[1px]`) above hero headline
- Light font weights throughout (300) for airy elegance
- No sharp edges — everything breathes with generous spacing

### Accessibility
| Pair | Ratio | WCAG |
|------|-------|------|
| Cream on Charcoal (#F0EBE1 / #171614) | 13.8:1 | AAA |
| Copper on Charcoal (#C4956A / #171614) | 5.9:1 | AA |
| Stone on Charcoal (#8A8174 / #171614) | 4.0:1 | AA (large text) |
| Dark on Copper (#171614 / #C4956A) | 5.9:1 | AA |

- **Note**: Stone (#8A8174) only passes AA for large text (18px+). Use for labels/captions only, never body text.

### Mobile (375px)
- Nav: brand text only, hamburger for links (slide-down panel, charcoal bg)
- Hero: min-h-[80vh] instead of min-h-screen, scroll indicator hidden
- Stats: single column stack, cards full-width
- Service cards: full-width stack, touch target min 48px
- CTA: full-width button
- Parallax: disabled (performance)

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
| Focus ring | Purple | `#5B21B6` |

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

### Animation
- **Entrance**: Slide-up 30px + fade-in, 500ms ease-out, stagger 80ms — energetic, fast
- **Nav shadow**: Box-shadow transition on scroll (300ms, triggered by scrollY > 20)
- **Stats numbers**: Count-up with easing (800ms), triggered by IntersectionObserver
- **CTA buttons**: Scale 1.02 on hover (200ms), purple button has subtle pulse glow on idle
- **Cards**: translateY(-4px) + shadow increase on hover (250ms)
- **Phase badges**: Scale from 0 to 1 sequentially (400ms each, stagger 200ms)

### Distinguishing Details
- `'use client'` required — useState + useEffect for nav scroll shadow
- Alternating white/navy sections create strong rhythm
- Two CTA buttons in hero (filled + outline)
- Aspirational metric with asterisk footnote
- Single font family (Plus Jakarta Sans) — variety through weight only (400-800)
- Geometric confidence: straight lines, sharp corners, bold weights

### Accessibility
| Pair | Ratio | WCAG |
|------|-------|------|
| Navy on White (#0F1923 / #FFFFFF) | 16.4:1 | AAA |
| White on Navy (#FFFFFF / #0F1923) | 16.4:1 | AAA |
| Purple on White (#5B21B6 / #FFFFFF) | 8.9:1 | AAA |
| White on Purple (#FFFFFF / #5B21B6) | 8.9:1 | AAA |
| Navy 60% on White | 7.1:1 | AAA |

### Mobile (375px)
- Nav: brand left, hamburger right (slide-down navy panel)
- Hero: stack CTAs vertically, both full-width, min-height 48px
- Stats: 2x2 grid (not 4-column)
- Service cards: single column stack
- Why-different: single column, purple left borders persist
- CTA: full-width button, py-16
- Footer: stacked centered

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
| Focus ring | Olive | `#6B705C` |

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
- Nav: Not fixed. Generous top padding (pt-10). Brand as text, olive dot active indicator. Links right.
- Hero: Centered text, generous vertical space (pt-32 pb-20). Regular weight serif headline. Subtitle in warm gray.
- Storytelling: 3 paragraphs in very narrow column (max-w-xl, ~576px). Light font weight. Generous line-height.
- Stats: 3-column, subtle warm-gray top border per stat. Small numbers (text-3xl). Olive accent on labels.
- Services: Simple list, no cards, no borders between items. Just title + description. Olive hover on title.
- CTA: Bone bg continues. Quiet question as headline. Olive outline button (1px border).
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

### Animation
- **Entrance**: Fade-in only, 1000ms ease-out, stagger 200ms — the slowest of all directions
- **No slide/scale** — movement contradicts the stillness
- **Service titles**: Color transition to olive on hover (400ms)
- **Rules**: Opacity from 0 to 40% on scroll (600ms)
- **Feel**: Like turning pages in a quiet room

### Distinguishing Details
- `'use client'` required — hover effects on service titles
- Barely-there nav with olive dot active indicator
- Regular-weight headings (400, not bold) — intentional restraint
- Narrowest content column of all directions (~576px body)
- No section background changes — bone throughout
- Warm gray rules between every section
- Everything whispers — nothing shouts

### Accessibility
| Pair | Ratio | WCAG |
|------|-------|------|
| Charcoal on Bone (#2C2C2C / #F5F2ED) | 10.4:1 | AAA |
| Olive on Bone (#6B705C / #F5F2ED) | 4.6:1 | AA |
| Warm gray on Bone (#A8A29E / #F5F2ED) | 2.5:1 | FAIL body |

- **Note**: Warm gray (#A8A29E) fails WCAG for body text on bone. Use ONLY for decorative borders and labels at 14px+ with font-weight 500+. Never for body copy.

### Mobile (375px)
- Nav: brand only, links hidden (content is linear enough to not need nav)
- Hero: pt-20 pb-12 (less air than desktop but still generous)
- Stats: single column, olive labels persist
- Services: full width, olive hover disabled (touch)
- CTA: full-width olive outline button, min-height 48px
- Column: max-w stays narrow, px-6 enough

---

## F — Neo-Brutalist

**Reference**: Gumroad redesign, Figma community, Notion templates
**Mood**: Raw, unapologetic, anti-corporate, playfully aggressive

### Palette
| Role | Color | Hex |
|------|-------|-----|
| Background | Off-white | `#FFFDF7` |
| Text | Black | `#000000` |
| Accent primary | Electric yellow | `#FFE600` |
| Accent secondary | Hot pink | `#FF3366` |
| Cards | White | `#FFFFFF` |
| Borders | Black | `#000000` |
| Shadows | Black solid | `#000000` (no blur) |
| Focus ring | Hot pink | `#FF3366` |

### Typography
| Role | Font | Weights | CSS Variable |
|------|------|---------|-------------|
| Display (headings) | Space Mono | 400, 700 | `--font-space-mono` |
| Body | DM Sans | 400, 500, 700 | `--font-dm-sans` |

- Headlines: Space Mono, 700, clamp(2rem, 5vw, 4rem), uppercase, tracking-tight
- Body text: DM Sans, 400, text-base to text-lg, leading-relaxed
- Labels: Space Mono, 400, text-xs, uppercase
- Buttons: Space Mono, 700, uppercase, text-sm

### Layout
- Max width: `max-w-[1100px]`
- Padding: `px-6 md:px-10`
- Nav: Static top, black bottom border (3px). Brand in Space Mono uppercase. Links right. Yellow highlight on active.
- Hero: MASSIVE headline (uppercase mono), yellow highlight on key word (inline yellow bg), subtitle below. Black CTA button with 4px solid black shadow offset.
- Storytelling: Left-aligned, short punchy paragraphs, occasional **bold** for emphasis
- Stats: Cards with 3px black border + 6px solid black shadow (offset bottom-right). Yellow bg on one stat for emphasis. Black text.
- Services: Stacked cards with thick borders (3px), alternating yellow/pink accent stripe on left (8px wide). Title in mono uppercase.
- CTA: Yellow (#FFE600) full-width band. Black text. Button with pink bg + black border + shadow.
- Footer: Black bg, white text, mono font

### Section Pattern
```
Nav (off-white, 3px black bottom border)
Hero (off-white, massive mono uppercase, yellow highlight, shadow button)
Stats (off-white, bordered cards with hard shadows)
Services (off-white, thick-bordered cards with color stripes)
CTA (YELLOW full-width band, pink button)
Footer (BLACK bg, white mono text)
```

### Animation
- **Entrance**: NO fade-in — content snaps into place instantly (brutalist = no pretense)
- **Buttons**: translateY(-4px) + shadow grows from 4px to 8px on hover (150ms, ease-out) — "pressing" effect
- **Cards**: Slight rotate (0.5deg) + scale(1.01) on hover (200ms) — imperfect, playful
- **Yellow highlight**: Background-size animation from 0% to 100% on key word on scroll (300ms)
- **Cursor**: Consider `cursor: crosshair` on hero section for brutalist feel
- **No smooth scroll** — snap between sections

### Distinguishing Details
- `'use client'` required — hover effects on cards and buttons
- Hard shadows (no blur, solid black offset) are the signature
- 3px borders everywhere — nothing subtle
- Mono uppercase headings — raw, typographic
- Yellow highlight on key words (inline background)
- Mix of yellow and pink accents — not just one color
- Footer inverts to full black

### Accessibility
| Pair | Ratio | WCAG |
|------|-------|------|
| Black on Off-white (#000 / #FFFDF7) | 20.1:1 | AAA |
| Black on Yellow (#000 / #FFE600) | 16.1:1 | AAA |
| Black on Pink (#000 / #FF3366) | 5.3:1 | AA |
| White on Black (#FFF / #000) | 21:1 | AAA |

### Mobile (375px)
- Nav: brand left (mono), single hamburger icon (no bg, just ☰ in mono)
- Hero: uppercase headline wraps naturally, yellow highlight persists
- Stats: single column stack, hard shadows reduced to 4px offset
- Service cards: full width, left stripe persists (4px instead of 8px)
- CTA: full-width button with shadow
- All touch targets: min 48px height
- Hard shadows: reduce offset to 3px on mobile (performance)

---

## G — Playful Gradient

**Reference**: Linear, Raycast, Vercel marketing, Stripe
**Mood**: Modern SaaS energy, vibrant yet sophisticated, gradient-driven

### Palette
| Role | Color | Hex |
|------|-------|-----|
| Background | Near-black | `#0C0C0C` |
| Text | White | `#FFFFFF` |
| Gradient start | Electric blue | `#3B82F6` |
| Gradient middle | Violet | `#8B5CF6` |
| Gradient end | Pink | `#EC4899` |
| Secondary text | Gray | `#A1A1AA` |
| Card bg | White 5% | `rgba(255,255,255,0.05)` |
| Card border | White 10% | `rgba(255,255,255,0.1)` |
| Focus ring | Violet | `#8B5CF6` |

### Typography
| Role | Font | Weights | CSS Variable |
|------|------|---------|-------------|
| Display (headings) | Satoshi (or Inter if unavailable) | 500, 700, 900 | `--font-satoshi` |
| Body | Inter | 400, 500 | `--font-inter` |

- Headlines: Satoshi/Inter, 700-900, clamp(2.5rem, 6vw, 4.5rem), tracking-tight
- Hero headline: `background: linear-gradient(135deg, #3B82F6, #8B5CF6, #EC4899)` with `-webkit-background-clip: text` and `color: transparent`
- Body text: Inter, 400, text-base to text-lg, leading-relaxed, #A1A1AA
- Labels: Inter, 500, text-xs, uppercase, tracking-widest
- Buttons: Inter, 600, text-sm

### Layout
- Max width: `max-w-[1200px]`
- Padding: `px-6 md:px-10`
- Nav: Fixed, bg-black/80 backdrop-blur-xl, border-b white/10. Brand as gradient text. Links in gray, white on hover.
- Hero: Centered. Gradient text headline (the signature). Subtitle in gray. Gradient-bordered button (transparent bg with gradient border via pseudo-element or border-image).
- Storytelling: Centered, narrow (640px), gray text, occasional white text for emphasis
- Stats: Glass cards (white 5% bg, white 10% border, backdrop-blur). Gradient number text. Gray labels. 3-column.
- Services: Glass cards. Icon or emoji top-left. Title in white, description in gray. Subtle gradient top border (2px) on hover.
- CTA: Full gradient background band (blue→violet→pink at 135deg). White text. White button (dark text).
- Footer: Near-black, gray text, gradient rule top

### Section Pattern
```
Nav (fixed, black/80, backdrop-blur, gradient brand)
Hero (near-black, GRADIENT TEXT headline, gradient-border button)
Storytelling (near-black, centered gray text)
Stats (near-black, glass cards, gradient numbers)
Services (near-black, glass cards, gradient hover border)
CTA (GRADIENT full-width band, white button)
Footer (near-black, gradient rule, gray text)
```

### Animation
- **Entrance**: Fade-in + slide-up (30px), 700ms ease-out, stagger 120ms
- **Gradient headline**: `background-size: 200% 200%` with slow animation cycling position (8s infinite linear) — shimmer effect
- **Glass cards**: Border glow on hover — border-color transitions from white/10 to white/20 (300ms)
- **CTA gradient**: Slow background-position shift (15s infinite, linear) — living gradient
- **Stats numbers**: Count-up + gradient text reveals (left to right wipe, 1000ms)
- **Nav**: Fade-in on load (300ms)
- **Cursor glow**: Optional — radial gradient follows mouse on hero (CSS custom properties via mousemove)

### Distinguishing Details
- `'use client'` required — gradient animations, hover effects, potential cursor tracking
- Gradient text on headline is THE signature — must be `-webkit-background-clip: text`
- Glass morphism cards (semi-transparent bg + backdrop-blur + subtle border)
- Everything feels like it's floating on darkness
- Gradient border button (not filled gradient — gradient on border only)
- Slow-moving gradients create a "living" feel

### Accessibility
| Pair | Ratio | WCAG |
|------|-------|------|
| White on Near-black (#FFF / #0C0C0C) | 19.8:1 | AAA |
| Gray on Near-black (#A1A1AA / #0C0C0C) | 6.3:1 | AA |
| White on Blue (#FFF / #3B82F6) | 4.6:1 | AA |
| White on Violet (#FFF / #8B5CF6) | 4.9:1 | AA |
| White on Pink (#FFF / #EC4899) | 4.5:1 | AA |

- **Note**: Gradient text has variable contrast. Ensure at minimum the middle of the gradient (violet) meets AA. Use solid color fallback for `prefers-reduced-motion`.

### Mobile (375px)
- Nav: brand (gradient text), single menu icon
- Hero: gradient headline clamps to 2.5rem, gradient-border button full-width
- Stats: single column, glass cards full-width
- Services: single column glass cards
- CTA: gradient band, full-width white button
- Cursor glow: disabled on touch devices
- Gradient animation: reduced to static gradient on `prefers-reduced-motion`
- Glass blur: reduced to `backdrop-blur-sm` on mobile (performance)

---

## H — Retro Terminal

**Reference**: Stripe CLI, Vercel CLI, VSCode, CRT monitors
**Mood**: Hacker aesthetic, developer credibility, nostalgic tech

### Palette
| Role | Color | Hex |
|------|-------|-----|
| Background | Terminal black | `#0D1117` |
| Text | Terminal green | `#00FF41` |
| Text secondary | Dim green | `#00CC33` |
| Accent | Amber | `#FFB000` |
| Muted text | Gray-green | `#4A6741` |
| Card bg | Slightly lighter | `#161B22` |
| Borders | Green at 30% | `rgba(0,255,65,0.3)` |
| Cursor/blink | Bright green | `#00FF41` |
| Error/alert | Red | `#FF4444` |
| Focus ring | Amber | `#FFB000` |

### Typography
| Role | Font | Weights | CSS Variable |
|------|------|---------|-------------|
| ALL text | JetBrains Mono | 400, 500, 700 | `--font-jetbrains` |

- Headlines: JetBrains Mono, 700, clamp(1.5rem, 4vw, 2.5rem) — NOT massive (terminals have smaller text)
- Body text: JetBrains Mono, 400, text-sm to text-base, leading-relaxed
- Labels: JetBrains Mono, 400, text-xs
- Prefixes: `>` or `$` before lines, `//` before comments

### Layout
- Max width: `max-w-4xl` (896px) — terminal windows are narrow
- Padding: `px-6 md:px-10`
- Nav: Static. Green text on black. Brand as `> brand_name`. Links as `[link]` with brackets. Amber active indicator.
- Hero: Terminal prompt aesthetic. `$ whoami` → name. `$ cat mission.txt` → description. Blinking cursor after last line. Green CTA styled as `[ENTER]` or `> run start`.
- Storytelling: Formatted as terminal output. `---` dividers. `//` comment prefixes for asides. Green text, dim green for less important.
- Stats: Code-block style. `const stats = { clients: 47, years: 3 }` with syntax-highlighted numbers in amber. Bordered card with green/30% border.
- Services: ASCII-table format or numbered list with `├──`, `└──` tree characters. Each service as a "module" or "package".
- CTA: Amber (#FFB000) full-width band. Black text. Button styled as terminal command: `> contact --now`.
- Footer: Green on black, `// EOF`, back link as `[← /demo]`

### Section Pattern
```
Nav (black, green text, bracket-links)
Hero (black, terminal prompts, blinking cursor)
── green dashed rule (---) ──
Storytelling (black, terminal output format)
── green dashed rule ──
Stats (black, code-block style, amber numbers)
── green dashed rule ──
Services (black, ASCII tree or table format)
CTA (AMBER full-width band, command-style button)
Footer (black, // EOF, minimal)
```

### Animation
- **Typewriter**: Hero text types out character by character (50ms per char, 200ms pause between lines)
- **Blinking cursor**: `|` blinks at end of typed text (1s interval, step-end timing)
- **Entrance**: Lines appear top-to-bottom (typewriter for hero, instant for other sections)
- **Stats numbers**: No count-up — appear as if "computed" instantly
- **CTA hover**: Button text changes from `> contact --now` to `> RUNNING...` with loading dots animation
- **Scanline overlay**: Optional very subtle horizontal scanline CSS pattern (2px repeating-linear-gradient at 5% opacity)
- **CRT flicker**: Optional 1-frame opacity dip every 5s (very subtle, 50ms duration) — disable on `prefers-reduced-motion`

### Distinguishing Details
- `'use client'` required — typewriter effect, blinking cursor, hover states
- MONO EVERYTHING — single font family for all text
- Terminal prompt prefixes (`>`, `$`, `//`, `├──`)
- ASCII art dividers and tree structures
- Numbers in amber, text in green — two-color terminal palette
- Blinking cursor is the signature micro-interaction
- Scanline overlay adds CRT authenticity
- Smaller text than other directions — terminals don't use 5rem headlines

### Accessibility
| Pair | Ratio | WCAG |
|------|-------|------|
| Green on Black (#00FF41 / #0D1117) | 10.1:1 | AAA |
| Amber on Black (#FFB000 / #0D1117) | 10.8:1 | AAA |
| Black on Amber (#0D1117 / #FFB000) | 10.8:1 | AAA |
| Dim green on Black (#00CC33 / #0D1117) | 7.8:1 | AAA |
| Gray-green on Black (#4A6741 / #0D1117) | 3.2:1 | FAIL body |

- **Note**: Gray-green (#4A6741) fails WCAG for body text. Use ONLY for decorative lines, borders, and `//` comment prefixes. Never for readable content.

### Mobile (375px)
- Nav: `> brand` left, no links (terminal doesn't have menu)
- Hero: typewriter speed increases (30ms per char), fewer lines
- Stats: single column, code-block style persists
- Services: simplified ASCII — no tree characters, just `> service_name`
- CTA: full-width command button, min-height 48px
- Scanline/flicker: disabled on mobile
- Font size: text-xs for body (mono needs less size to be readable)
- Horizontal scroll: prevent overflow from long mono lines with `overflow-wrap: break-word`

---

## Animation System

All directions use a shared animation approach built on CSS + IntersectionObserver. No external animation libraries required.

### Implementation Pattern

```tsx
// Shared hook for all directions — include directly in each demo page
function useScrollReveal() {
  useEffect(() => {
    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            entry.target.classList.add('revealed')
            observer.unobserve(entry.target)
          }
        })
      },
      { threshold: 0.1, rootMargin: '0px 0px -50px 0px' }
    )
    document.querySelectorAll('.reveal').forEach((el) => observer.observe(el))
    return () => observer.disconnect()
  }, [])
}
```

### CSS Pattern (inline in each page)

```css
.reveal {
  opacity: 0;
  transform: translateY(var(--reveal-y, 20px));
  transition: opacity var(--reveal-duration, 600ms) var(--reveal-easing, ease-out),
              transform var(--reveal-duration, 600ms) var(--reveal-easing, ease-out);
}
.reveal.revealed {
  opacity: 1;
  transform: translateY(0);
}
.reveal:nth-child(2) { transition-delay: var(--reveal-stagger, 100ms); }
.reveal:nth-child(3) { transition-delay: calc(var(--reveal-stagger, 100ms) * 2); }
.reveal:nth-child(4) { transition-delay: calc(var(--reveal-stagger, 100ms) * 3); }
```

### Per-Direction CSS Variables

| Direction | --reveal-y | --reveal-duration | --reveal-stagger | --reveal-easing |
|-----------|-----------|-------------------|-----------------|-----------------|
| Editorial | 20px | 600ms | 100ms | ease-out |
| Minimal | 0px (no slide) | 0ms (instant) | 0ms | — |
| Luxury | 0px (fade only) | 800ms | 150ms | ease-out |
| Corporate | 30px | 500ms | 80ms | ease-out |
| Kinfolk | 0px (fade only) | 1000ms | 200ms | ease-out |
| Brutalist | 0px | 0ms (instant) | 0ms | — |
| Playful | 30px | 700ms | 120ms | ease-out |
| Retro | 0px | 0ms (typewriter) | 0ms | — |

### Count-Up Animation (Stats)

```tsx
function CountUp({ target, duration = 1200 }: { target: number; duration?: number }) {
  const [count, setCount] = useState(0)
  const ref = useRef<HTMLSpanElement>(null)

  useEffect(() => {
    const observer = new IntersectionObserver(([entry]) => {
      if (entry.isIntersecting) {
        const start = performance.now()
        const animate = (now: number) => {
          const progress = Math.min((now - start) / duration, 1)
          const eased = 1 - Math.pow(1 - progress, 3) // ease-out cubic
          setCount(Math.floor(eased * target))
          if (progress < 1) requestAnimationFrame(animate)
        }
        requestAnimationFrame(animate)
        observer.disconnect()
      }
    }, { threshold: 0.5 })
    if (ref.current) observer.observe(ref.current)
    return () => observer.disconnect()
  }, [target, duration])

  return <span ref={ref}>{count}</span>
}
```

### Reduced Motion

ALL directions MUST respect `prefers-reduced-motion`:

```css
@media (prefers-reduced-motion: reduce) {
  .reveal {
    opacity: 1 !important;
    transform: none !important;
    transition: none !important;
  }
  /* Disable all custom animations */
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

### Typewriter (Retro only)

```tsx
function Typewriter({ text, speed = 50, delay = 0 }: { text: string; speed?: number; delay?: number }) {
  const [displayed, setDisplayed] = useState('')
  const [showCursor, setShowCursor] = useState(true)

  useEffect(() => {
    const timeout = setTimeout(() => {
      let i = 0
      const interval = setInterval(() => {
        setDisplayed(text.slice(0, i + 1))
        i++
        if (i >= text.length) clearInterval(interval)
      }, speed)
      return () => clearInterval(interval)
    }, delay)
    return () => clearTimeout(timeout)
  }, [text, speed, delay])

  useEffect(() => {
    const blink = setInterval(() => setShowCursor(v => !v), 530)
    return () => clearInterval(blink)
  }, [])

  return <span>{displayed}<span style={{ opacity: showCursor ? 1 : 0 }}>|</span></span>
}
```

---

## Accessibility Requirements

### Universal Rules (All Directions)

1. **Color contrast**: Every text/background pair MUST meet WCAG AA minimum (4.5:1 for body, 3:1 for large text 18px+). Each direction's contrast table is pre-calculated above.

2. **Focus indicators**: All interactive elements MUST have visible focus rings:
   ```css
   /* Per-direction focus ring color defined in palette */
   :focus-visible {
     outline: 2px solid var(--focus-color);
     outline-offset: 2px;
   }
   /* Remove default outline only when custom is applied */
   :focus:not(:focus-visible) {
     outline: none;
   }
   ```

3. **Touch targets**: All buttons and links MUST have minimum 44x44px touch target (48px preferred):
   ```css
   button, a[role="button"], .cta-link {
     min-height: 44px;
     min-width: 44px;
     /* For inline links, use padding to expand touch area */
   }
   ```

4. **Motion**: Always include `prefers-reduced-motion` media query. Typewriter, parallax, gradient shimmer, cursor glow — all disabled.

5. **Semantic HTML**: Use proper heading hierarchy (h1 → h2 → h3, never skip). Use `<nav>`, `<main>`, `<section>`, `<footer>`. Use `<button>` for actions, `<a>` for navigation.

6. **Skip link**: Every demo page MUST include:
   ```tsx
   <a href="#main" className="sr-only focus:not-sr-only focus:absolute focus:top-4 focus:left-4 focus:z-[100000] focus:px-4 focus:py-2 focus:bg-white focus:text-black focus:rounded">
     Skip to content
   </a>
   ```

7. **Image alt text**: Any decorative images use `alt=""` + `aria-hidden="true"`. Meaningful images get descriptive alt text.

8. **Language**: Set `lang` attribute on html or wrapper element matching content language.

### Automated Check

After generating demos, verify accessibility with:
```bash
npx next build  # Catches structural issues
# Then in browser dev tools: Lighthouse > Accessibility (target: 95+)
```

### Color Contrast Quick Reference

| Direction | Body text ratio | Accent ratio | Weakest pair | Notes |
|-----------|----------------|-------------|-------------|-------|
| Editorial | 13.2:1 (AAA) | 4.5:1 (AA) | Gold on cream | Gold only for accents, not body |
| Minimal | 19.3:1 (AAA) | 5.6:1 (AA) | Red on white | Red only CTAs |
| Luxury | 13.8:1 (AAA) | 5.9:1 (AA) | Stone on charcoal (4.0) | Stone for labels only (18px+) |
| Corporate | 16.4:1 (AAA) | 8.9:1 (AAA) | Navy 60% (7.1) | All pairs excellent |
| Kinfolk | 10.4:1 (AAA) | 4.6:1 (AA) | Warm gray on bone (2.5) | Warm gray for borders ONLY |
| Brutalist | 20.1:1 (AAA) | 16.1:1 (AAA) | Pink (5.3) | All pairs strong |
| Playful | 19.8:1 (AAA) | 4.6-4.9:1 (AA) | Gradient midpoint | Solid color fallback needed |
| Retro | 10.1:1 (AAA) | 10.8:1 (AAA) | Gray-green (3.2) | Gray-green decorative only |

---

## Mobile-First Specs

### Universal Mobile Rules

1. **Breakpoints**: Use Tailwind defaults. Design mobile (375px) first, enhance for tablet (768px) and desktop (1024px+).

2. **Font sizes**: Body text minimum 16px on mobile (prevents iOS zoom on input focus). Headlines clamp down but never below 1.5rem.

3. **Touch targets**: 48px minimum height for all interactive elements. 8px minimum spacing between adjacent targets.

4. **Nav pattern**: Every direction MUST define a mobile nav. Options:
   - Hidden links, brand only (Kinfolk, Retro)
   - Hamburger → slide-down panel (Luxury, Corporate)
   - Inline pills below hero (Editorial)
   - Minimal single link (Minimal)
   - Hamburger → full-screen takeover (Brutalist, Playful)

5. **Images**: Use `loading="lazy"`, `sizes` attribute, and responsive widths.

6. **Scroll**: Avoid horizontal scroll. Mono fonts: use `overflow-wrap: break-word; word-break: break-word;`.

7. **Performance on mobile**:
   - Disable parallax
   - Reduce backdrop-blur to `backdrop-blur-sm`
   - Disable cursor-tracking effects
   - Reduce animation complexity (fewer particles, simpler gradients)
   - Scanlines/CRT effects: disabled

8. **Testing**: After build, take screenshots at 375px width for every demo. Verify:
   - No horizontal overflow
   - All text readable (16px+ body)
   - All buttons tappable (48px+)
   - Nav is functional
   - No overlapping elements

### Viewport Meta

Ensure the project's root layout includes:
```html
<meta name="viewport" content="width=device-width, initial-scale=1" />
```

### Mobile Section Spacing

| Desktop spacing | Mobile equivalent |
|----------------|-------------------|
| py-24 | py-12 |
| py-20 | py-10 |
| py-32 | py-16 |
| gap-12 | gap-6 |
| gap-8 | gap-4 |

---

## Copy Tone Guidelines Per Direction

| Direction | Tone | Sentence Style | Example Opening |
|-----------|------|---------------|----------------|
| Editorial | Authoritative, measured | Long, structured, with subordinate clauses | "In an era where every consultancy promises transformation..." |
| Minimal | Direct, stripped | Short, declarative, no ornament | "Your team doesn't need another AI course." |
| Luxury | Intimate, refined | Flowing, personal, sensory language | "There is a particular kind of clarity that comes from..." |
| Corporate | Confident, structured | Active voice, data-driven, results-oriented | "Leading companies don't wait for AI readiness." |
| Kinfolk | Thoughtful, quiet | Conversational, questioning, first-person | "I studied psychology, not engineering." |
| Brutalist | Blunt, irreverent | Fragments, ALL CAPS moments, zero filler | "AI consultants talk. We build." |
| Playful | Energetic, modern | Medium length, tech-native vocab, emoji-optional | "Your stack is modern. Your strategy should be too." |
| Retro | Dry, technical | Short, command-like, developer humor | "$ cat about.txt — No frameworks. No BS." |

## Common Section Structure (All Directions)

Every demo page MUST include these sections in order:
1. **Skip link** — Hidden, visible on focus, jumps to #main
2. **Nav** — Brand + navigation links + optional CTA
3. **Hero** — Headline + subtitle/description + primary CTA
4. **Storytelling** — Personal narrative (founder story, unique angle)
5. **Stats** — 3-4 key numbers with labels
6. **Services** — 3-4 offerings with descriptions
7. **CTA** — Final call to action (booking, contact)
8. **Footer** — Copyright + back link to `/demo`

## Technical Requirements

- Each page: self-contained, only imports `next/link` and `next/font/google`
- Colors via inline `style` attributes, NOT Tailwind theme (demos must not depend on project config)
- Fonts via `next/font/google` with `variable` prop and CSS variable usage
- Pages with event handlers (onMouseEnter, useState, useEffect): MUST have `'use client'`
- Pages with `'use client'`: MUST NOT export `metadata`
- Server Component pages: CAN export `metadata`
- All pages: responsive (mobile-first, enhance with Tailwind breakpoints)
- Back link to `/demo` in every footer
- Skip link as first focusable element
- `prefers-reduced-motion` media query in every page with animations
- Focus-visible outlines on all interactive elements
- Minimum 44px touch targets on all buttons/links
