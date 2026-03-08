# UX/UI Premium Direction Style Selector — Claude Code Skill

Deploy 8 radically different visual direction demos for any Next.js + Tailwind CSS project. Compare side-by-side, choose your aesthetic, then auto-generate production-ready theme tokens and components.

## What it does

When invoked, this skill:

1. **Generates 5-8 demo pages** under `/demo/` — each a complete page with a distinct visual identity
2. **You pick your favorite** — compare typography, color, layout, animation side-by-side
3. **Applies your choice** — generates Tailwind config, CSS variables, and base components matching the chosen direction

### The 8 Directions

| Direction | Reference | Mood | Best For |
|-----------|-----------|------|----------|
| **Editorial Serif** | The Economist, Monocle | Intellectual authority | Consulting, media, thought leadership |
| **Swiss Minimal** | Dieter Rams, Braun | Functional clarity | SaaS, tools, developer products |
| **Luxury Dark Warm** | Aesop, Byredo | Intimate warmth | Premium services, hospitality |
| **Corporate Bold** | Accenture, McKinsey | Structured confidence | Enterprise, B2B |
| **Understated Elegance** | Kinfolk, Cereal | Editorial calm | Creative, wellness, editorial |
| **Neo-Brutalist** | Gumroad redesign | Raw irreverence | Startups, creative agencies |
| **Playful Gradient** | Linear, Stripe | Modern SaaS energy | SaaS, tech startups |
| **Retro Terminal** | Stripe CLI, VSCode | Hacker credibility | Developer tools, CLI products |

Each direction includes complete specs for:
- Color palette with WCAG contrast ratios
- Typography (Google Fonts, weights, sizes)
- Layout patterns and section structure
- Animation system (scroll reveal, hover, micro-interactions)
- Mobile-first responsive specs (375px → 1280px)
- Accessibility (focus states, touch targets, reduced-motion)

## Installation

```bash
npx skills add Luispitik/ux-ui-premium-direction-style-selector@ux-ui-premium-direction-style-selector
```

Or install globally:

```bash
npx skills add Luispitik/ux-ui-premium-direction-style-selector@ux-ui-premium-direction-style-selector -g -y
```

## Usage

In Claude Code, say any of:
- "style selector"
- "choose styles"
- "visual alternatives"
- "pick a design direction"
- "compare different aesthetics"

### Smart Direction Selection

The skill auto-selects the 5 most relevant directions based on your project type:

| Project Type | Recommended Directions |
|-------------|----------------------|
| Landing page | Editorial, Minimal, Luxury, Corporate, Kinfolk |
| SaaS / Web app | Minimal, Corporate, Playful, Brutalist, Retro |
| E-commerce | Minimal, Luxury, Corporate, Playful, Kinfolk |
| Dashboard | Minimal, Corporate, Playful, Retro, Brutalist |
| Portfolio | Editorial, Luxury, Kinfolk, Brutalist, Playful |
| Developer tools | Minimal, Brutalist, Retro, Playful, Corporate |

Say "show all 8" to see every direction regardless of project type.

### Post-Selection: Apply Direction

After choosing, the skill generates:
- **`tailwind.config.ts`** — Theme tokens (colors, fonts, animations)
- **`globals.css`** — CSS variables + reduced-motion media query
- **Base components** — Button, Card, Section, Container, Nav, ScrollReveal
- **Font setup** — next/font/google configuration in root layout

Then cleans up the `/demo/` directory and verifies the build.

## Project Type Adaptations

Beyond landing pages, the skill adapts demo structure for:

- **Web App / SaaS** — Feature showcase, how-it-works flow, pricing tiers
- **Dashboard** — Data visualization mock, sidebar nav, data table
- **E-commerce** — Product grid, categories, trust signals
- **Portfolio** — Project grid, about section, testimonials

## Requirements

- Next.js App Router project
- Tailwind CSS configured
- `src/app/` directory structure

## What's Included

```
ux-ui-premium-direction-style-selector/
  SKILL.md                      # Main skill (workflow, steps 1-10)
  references/
    directions.md               # Complete specs for all 8 directions
                                #   - Palettes with hex codes
                                #   - Typography (fonts, weights, sizes)
                                #   - Layout patterns
                                #   - Animation system + code snippets
                                #   - Accessibility (contrast ratios, focus)
                                #   - Mobile-first specs (375px)
                                #   - Copy tone guidelines
```

## Built-In Accessibility

Every generated demo includes:
- WCAG AA color contrast (pre-calculated per direction)
- Focus-visible outlines on all interactive elements
- Skip-to-content link
- Semantic HTML (proper heading hierarchy, landmarks)
- `prefers-reduced-motion` support (all animations disabled)
- 44px+ touch targets on mobile
- Proper `lang` attribute

## Built-In Animation System

Each direction has a unique animation personality:

| Direction | Animation Style |
|-----------|----------------|
| Editorial | Fade + slide-up, gold rules expand |
| Minimal | **No animations** — Rams: "as little design as possible" |
| Luxury | Slow fade only (800ms), cinematic parallax on hero |
| Corporate | Fast slide-up (500ms), count-up stats, card hover lift |
| Kinfolk | Slowest fade (1000ms), no movement — stillness |
| Brutalist | **Instant appear** — cards rotate on hover, hard shadow grow |
| Playful | Gradient shimmer, glass glow, cursor tracking on hero |
| Retro | Typewriter effect, blinking cursor, optional CRT scanlines |

All animations respect `prefers-reduced-motion` automatically.

## Author

Created by [Luis Salgado](https://salgadoia.com) — AI consultant helping businesses adopt AI with strategy, not hype.

## License

MIT
