---
name: style-selector
description: >
  Deploy 5 radically different visual direction demos for a website or webapp project.
  Creates self-contained Next.js pages under /demo/ with distinct identities (typography,
  color palette, layout) so the user can compare and choose a visual direction.
  Use when: starting a new web project, redesigning a site, choosing visual direction,
  the user says "style selector", "choose styles", "visual alternatives", "pick a design
  direction", or wants to compare different aesthetic approaches before committing to one.
  Works with Next.js + Tailwind CSS projects.
---

# Style Selector

Generate 5 self-contained visual direction demo pages for comparison.

## Workflow

### 1. Gather project context

Before generating demos, collect:
- **Business type** (consulting, SaaS, e-commerce, portfolio, etc.)
- **Business name and tagline**
- **Key stats** (numbers to display -- users, clients, years, etc.)
- **Services/products** (3-4 items with short descriptions)
- **CTA** (primary call to action -- book a call, sign up, buy, etc.)
- **Language** (Spanish, English, etc.)
- **Tone** (corporate, friendly, luxury, technical, etc.)

If the project already has content (existing pages, spec docs, CLAUDE.md), extract this context automatically without asking.

### 2. Verify project setup

Confirm the project uses Next.js App Router + Tailwind CSS. Check:
- `src/app/` or `app/` directory exists
- `tailwind.config.ts` or `tailwind.config.js` exists
- `globals.css` has `@tailwind base/components/utilities` directives

**Critical**: Ensure globals.css custom styles are wrapped in `@layer base { }`. Unlayered CSS overrides Tailwind utility classes due to CSS cascade layers. If `* { margin: 0; padding: 0; }` or `body { ... }` exist outside a `@layer`, wrap them in `@layer base { }`.

### 3. Create demo infrastructure

Create these files:

**Demo layout** (`src/app/demo/layout.tsx`):
```tsx
'use client'
export default function DemoLayout({ children }: { children: React.ReactNode }) {
  return (
    <div style={{ position: 'fixed', inset: 0, zIndex: 99999, overflow: 'auto', background: '#ffffff', fontFamily: 'system-ui, sans-serif', color: '#000' }}>
      <style>{\`body { overflow: hidden !important; }\`}</style>
      {children}
    </div>
  )
}
```

**Demo index page** (`src/app/demo/page.tsx`): A 'use client' page listing all 5 directions as clickable cards. Each card shows: direction name, subtitle/reference, description, and 4 color swatches. Dark background (#0a0a0a) for the index page.

### 4. Generate 5 demo pages

See `references/directions.md` for the complete spec of each visual direction.

Each demo page must be:
- **Self-contained** (no shared component imports -- only `next/link` and `next/font/google`)
- **Responsive** (mobile + desktop via Tailwind breakpoints)
- **Complete** (nav + hero + storytelling + stats + services + CTA + footer)
- **Unique fonts** via `next/font/google` with CSS variables
- **Custom colors** via inline `style` attributes (not relying on project's Tailwind theme)
- **Back link** to `/demo` in the footer

Pages that use event handlers (onMouseEnter, useState, useEffect) MUST have `'use client'` at the top. Pages with `'use client'` MUST NOT export `metadata`.

Generate all 5 pages in parallel using Task agents for speed.

### 5. Adapt copy to project

For each direction, rewrite copy to match the project's context:
- Headline adapted to the business and tone
- Storytelling adapted to the founder/company narrative
- Stats using real project numbers
- Services listing real offerings
- CTA pointing to real contact mechanism

**Copy quality rules** (avoid AI-sounding text):
- Use imperfect, conversational sentences
- Include specific details, not generic buzzwords
- Short paragraphs, varied rhythm
- Opinions and personality over corporate speak
- Questions to the reader
- First person where appropriate

### 6. Build and verify

Run `npx next build` to confirm all demo routes compile. Fix any errors:
- Missing `'use client'` for pages with event handlers
- `metadata` export in client components (remove it)
- Unused variables (remove them)

Start dev server and take screenshots of each demo to verify rendering.

### 7. Present to user

Show the user the demo index URL (`/demo`) and a summary table of all 5 directions with their visual identity. Ask which direction they prefer or if they want to mix elements.

## The 5 Directions

| ID | Name | Reference | Bg | Accent | Fonts |
|----|------|-----------|-----|--------|-------|
| editorial | Editorial Serif | The Economist | Cream #FAFAF5 | Gold #B8860B | Playfair Display + Source Serif 4 |
| minimal | Swiss Minimal | Dieter Rams | White #FFFFFF | Red #D42B2B | Space Grotesk + Inter |
| luxury | Luxury Dark Warm | Aesop | Charcoal #171614 | Copper #C4956A | Cormorant Garamond + Outfit |
| corporate | Corporate Bold | Accenture | White/Navy #0F1923 | Purple #5B21B6 | Plus Jakarta Sans |
| kinfolk | Understated Elegance | Kinfolk | Bone #F5F2ED | Olive #6B705C | Libre Baskerville + Karla |

For detailed specs (full palette, layout structure, section patterns, font weights), read `references/directions.md`.
