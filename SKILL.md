---
name: frontend-design-power-skill
description: >
  Master frontend design skill synthesized from 109 ui-skills.com skills.
  30 visual themes, WCAG contrast enforcement, 20 banned AI patterns,
  page architecture variation, animation decision framework, responsive
  design guidelines. Use for ANY frontend UI work.
---

# Frontend Design Power Skill

This skill is the result of scanning all 109 skills on ui-skills.com and
line-by-line analysis of the 9 most critical ones (baseline-ui, impeccable,
make-interfaces-feel-better, fixing-accessibility, fixing-motion-performance,
taste-skill, soft-skill, brutalist-skill, emil-design-eng) from their GitHub repos.

---

## 0. META: Never Default to AI Aesthetics

The AI's default aesthetic is well known: Inter font, purple-to-blue gradient,
rounded-lg cards, 1rem padding, centered hero, three equal feature cards,
tiny uppercase eyebrow on every section, 01/02/03 numbered markers.

**Every design decision must have a reason.** "Default" is never a reason.

### 0.1 Variance Mandate

> **Never produce the same design twice.** For different projects, different
> users, different requests — pick a DIFFERENT style, DIFFERENT layout,
> DIFFERENT color palette every time. Choose a DIFFERENT theme from the 30
> in Section 18 for each project. Never use the same theme twice in a row.

Behaviors that violate this rule:
- Jumping to Clean SaaS every time you see "B2B"
- Always picking Swiss Modern for "modern"
- Always doing centered hero + 3 cards for landing pages

**Correct approach:** Pick 2-3 candidate styles from the Section 18.10 table,
choose the one that fits best but is NOT the most obvious for that product type.

### 0.2 Page Architecture Variation (Anti-Template Rule)

> **Never use the same page skeleton twice.** The AI's default landing page
> template is: Nav → Centered Hero → 3-Card Grid → "Why Us" →
> CTA → Footer. REJECT this skeleton and choose a different architecture.

**Mandatory variation areas (change at least 3 per project):**

#### Hero Variations (pick different each project)
| Type | Description |
|------|-------------|
| A. **Centered text** | Classic centered heading + CTA |
| B. **Split** | Left text + right visual/product |
| C. **Full-bleed image** | Full screen visual, text overlay |
| D. **Type-only** | Typography only, no images |
| E. **Immediate product** | No hero, start directly with product grid |
| F. **Video/animated bg** | Moving background |
| G. **Masonry/Bento hero** | Card grid as hero |

#### Navigation Variations
| Type | Description |
|------|-------------|
| 1. **Top fixed** | Fixed top bar |
| 2. **Floating pill** | Centered floating capsule nav |
| 3. **Sidebar** | Left/right vertical navigation |
| 4. **Bottom** | Mobile-style bottom navigation |
| 5. **Hamburger-only** | Menu icon only, clean page |
| 6. **None** | No navigation, single page |

#### Section Order (shuffle per project)
Even with the same content, change the ORDER of sections:
- Features on top, hero at the bottom
- CTA in the middle, testimonials at the very top
- Mini-hero near the footer

#### Content Density (different per project)
| Density | Characteristic |
|---------|---------------|
| **Airy** | Few sections (3-4), ample whitespace, each section full screen |
| **Dense** | Many sections (7+), compact, fast scroll |
| **Hybrid** | 1 airy hero + dense content |

**Explicitly declare these decisions per project:**
```
[ ] Hero type: A / B / C / D / E / F / G (NOT the most obvious for this product)
[ ] Nav type: 1 / 2 / 3 / 4 / 5 / 6 (NOT the most obvious for this product)
[ ] Section order: [write the order]
[ ] Density: Airy / Dense / Hybrid
[ ] Style: pick 2-3 candidates from 18.10, choose the SECOND best, NOT the most obvious
```
> **What is "most obvious"?** SaaS → Clean SaaS, game → Deep Tech, portfolio → Editorial Minimal. When you see these, SKIP them, pick the next one. For SaaS, pick Graphite or Soft Structuralism instead of Clean SaaS. For games, pick Cyberpunk or Vaporwave instead of Deep Tech.

---

## 1. BRIEF INFERENCE — Read the Room First (taste-skill)

Before writing any code, **infer the design direction:**

### 1.1 Read These Signals
1. Page type (landing / portfolio / redesign / editorial)
2. Vibe words the user used
3. Reference URLs, screenshots, competitor brands
4. Target audience (B2B procurement vs design-conscious consumer vs recruiter)
5. Existing brand assets (logo, color, font, photography)
6. Quiet constraints (accessibility-first, public-sector, regulated)

### 1.2 Output a "Design Read"
Before any code, state in one line:
> "Reading this as: [page type] for [audience], with a [language], leaning toward [stack]."

Example: *"Reading this as: B2B SaaS landing for technical buyers, with a Linear-style minimalist language, leaning toward Tailwind + Geist + restrained motion."*

### 1.3 If Ambiguous, Ask
Ask exactly **one** question. Never a multi-question dump.

---

## 2. 3-DIAL SYSTEM — Design DNA (taste-skill)

Every design decision is governed by these three dials:

| Dial | 1 | 10 | Default |
|------|---|---|---------|
| **DESIGN_VARIANCE** | Perfect symmetry | Artistic chaos | 8 |
| **MOTION_INTENSITY** | Static | Cinematic / physics | 6 |
| **VISUAL_DENSITY** | Art gallery / airy | Cockpit / data-packed | 4 |

### 2.1 Dial Inference

| Signal | VARIANCE | MOTION | DENSITY |
|--------|----------|--------|---------|
| "minimalist / clean / calm / editorial / Linear-style" | 5-6 | 3-4 | 2-3 |
| "premium consumer / Apple-y / luxury / brand" | 7-8 | 5-7 | 3-4 |
| "playful / wild / Dribbble / Awwwards / experimental" | 9-10 | 8-10 | 3-4 |
| "landing page / portfolio (default)" | 7-9 | 6-8 | 3-5 |
| "trust-first / public-sector / accessibility-critical" | 3-4 | 2-3 | 4-5 |
| "redesign - preserve" | match existing | +1 | match existing |
| "redesign - overhaul" | +2 | +2 | match existing |

---

## 3. TYPOGRAPHY

### 3.1 Hierarchy (At least 3 levels)
```
Display  — hero, landing (2-3 uses max)
Heading  — section titles
Body     — text content
Label    — button, input, badge
```

### 3.2 Golden Rules
- **Max 2 font families.** Pair on contrast axis (serif + sans, geometric + humanist). Two geometric sans fonts = mistake.
- **Line-height:** heading 1.1-1.3, body 1.5-1.6
- **Letter-spacing:** heading -0.02em, body 0. Display floor ≥ **-0.04em** (below that = cramped).
- **Measure:** body max 65-75 characters
- `text-wrap: balance` on headings, `text-wrap: pretty` on body
- `font-variant-numeric: tabular-nums` for data/counters
- **Never** modify `letter-spacing` unless explicitly requested (baseline-ui)

### 3.3 Banned Fonts (soft-skill)
Inter, Roboto, Arial, Open Sans, Helvetica → don't use in premium projects.
Instead: Geist, Clash Display, PP Editorial New, Plus Jakarta Sans.

---

## 4. COLOR SYSTEMS (OKLCH)

### 4.1 Palette Architecture
```
Brand       — 1 primary color
Neutral     — 8-10 tones (50..950)
Accent      — 1 highlight (optional)
Semantic    — success, warning, error, info
```

### 4.2 The 2026 AI Default: Cream/Sand Body BG (impeccable)
OKLCH L 0.84-0.97, C < 0.06, hue 40-100 → cream, sand, bone, flour, linen,
parchment, wheat, biscuit, ivory. **Even the token names smell like AI**
(`--paper`, `--cream`, `--sand`).

> If the brief says "warm, traditional" do NOT translate that to a warm-tinted
> body bg. Instead: (a) saturated brand color as body, (b) chroma 0 off-white,
> or (c) darker mid-tone neutral in the brand's own hue.

### 4.3 Tinted Neutrals
Add chroma **toward the brand's own hue** at 0.005-0.015. Don't default-tint
toward warm "because the brand feels that way" — that's cross-project monoculture.

### 4.4 Color Strategy: 4 Commitment Levels (impeccable)

| Level | Description | When |
|-------|-------------|------|
| **Restrained** | Tinted neutrals + single accent ≤10% | Product default |
| **Committed** | One saturated color covers 30-60% of surface | Identity pages |
| **Full palette** | 3-4 named roles, each deliberate | Campaigns, data viz |
| **Drenched** | The surface IS the color | Heroes, campaigns |

### 4.5 Dark vs Light: Physical Scene Question (impeccable)
Before choosing, write one sentence:
> "Who uses this, where, under what ambient light, in what mood?"

If the sentence doesn't force the answer, it's not concrete enough.

### 4.6 Contrast
- Body text ≥ 4.5:1, large text ≥ 3:1
- **Placeholder text also needs 4.5:1** (muted-gray default fails — the most common failure)
- Gray text + colored BG = washed out. Use a darker shade of the BG's own hue
- Never convey meaning by color alone

---

## 5. SPACING AND GRID

### 5.1 Spatial Scale (4px base)
```
4px   — icon padding, inline gap
8px   — inner padding, adjacent elements
16px  — standard padding, card interior
24px  — section interior spacing
32px+ — between sections
```
Be consistent. No 13px, 7px values.

### 5.2 Macro-Whitespace (soft-skill)
Section padding: `py-24` to `py-40`. Let the design breathe.

### 5.3 Behavior
- Flexbox for 1D, Grid for 2D. Don't default to Grid when `flex-wrap` works
- Responsive grids: `repeat(auto-fit, minmax(280px, 1fr))`
- Cards are lazy. Nested cards = always wrong
- `size-*` for square elements (baseline-ui)

### 5.4 Card Grid Consistency

When building asymmetric grids, never make these mistakes:

| Mistake | Result | Fix |
|---------|--------|-----|
| 1 card 2fr + 4 cards 1fr side by side | Widths too different, visually unbalanced | All cards same width, OR asymmetry is intentional and meaningful |
| `grid-column: 1 / 3` + others 1fr | Featured card 2x wide, others squeezed | Featured card must have DIFFERENT content (image + text), not just "asymmetric for the sake of it" |
| 5 cards in 3-column grid | Last row has 2 centered cards, 1 empty slot | Card count should divide evenly into columns, or use `auto-fill` |
| 1-column mobile, 3-column desktop | Content order breaks (1-2-3 vs 1-4-2-5-3-6) | Preserve content flow, NEVER use `grid-auto-flow: dense` |

**Card grid checklist:**
```
[ ] All cards same width? If not, is ASYMMETRY intentional and meaningful?
[ ] Card count divisible by column count?
[ ] Does card order break on mobile?
[ ] Equal inner padding on all cards?
[ ] Consistent gap between cards?
```

### 5.5 Grid Strategy by Card Count

`auto-fit` doesn't always produce correct results. Choose a DELIBERATE grid based on card count:

| Card count | Desktop grid | Tablet | Mobile |
|------------|-------------|--------|--------|
| 2 | `repeat(2, 1fr)` | `repeat(2, 1fr)` | `1fr` |
| 3 | `repeat(3, 1fr)` | `repeat(3, 1fr)` | `1fr` |
| 4 | **`repeat(2, 1fr)`** ← 2×2 | `repeat(2, 1fr)` | `1fr` |
| 5 | `repeat(3, 1fr)` (3+2) or 3+2 asymmetric | `repeat(2, 1fr)` → 2+2+1 | `1fr` |
| 6 | `repeat(3, 1fr)` (2 rows) | `repeat(2, 1fr)` (3 rows) | `1fr` |
| 7+ | `repeat(auto-fit, minmax(300px, 1fr))` | `repeat(2, 1fr)` | `1fr` |

> **Golden rule:** 4 cards = 2×2. Never leave 3+1 orphan. 5 cards = 3+2 is fine but 2+2+1 is not.
> Only use `auto-fit` for 7+ cards or when the exact count is unknown.

---

## 6. DOUBLE-BEZEL ARCHITECTURE (soft-skill)

Premium cards, images, or containers are never placed flat on the background.
They must look like physical, machined hardware using nested enclosures:

```
Outer Shell (bg-black/5, ring-1, p-1.5, rounded-[2rem])
  └── Inner Core (own bg, shadow-[inset_0_1px_1px_white/15],
       rounded-[calc(2rem-0.375rem)])
```

### Button-in-Button (soft-skill)
Trailing icons never sit bare next to text. They go in their own circular wrapper:
```html
<span class="w-8 h-8 rounded-full bg-black/5 flex items-center justify-center">↗</span>
```

### 6.1 Button Quality Control

Never make these button mistakes:

| Mistake | Result | Fix |
|---------|--------|-----|
| `line-height: 1` + icon wrapper different size | Text baseline shifts, icon and text don't align | `line-height: 1.2` or match icon wrapper height |
| `scale(0.97)` + `inline-flex` icon | Icon shrinks, text appears to stay in place | Scale the entire button, add `flex-shrink: 0` to icon wrapper |
| Asymmetric `padding` (left 1rem, right doesn't match icon) | Unbalanced text-to-icon spacing | Equal left/right padding, gap independent of icon wrapper |
| `min-height: 44px` but `line-height: 1` | Text not vertically centered, sticks to top | `display: inline-flex; align-items: center` + sufficient padding |
| Icon wrapper missing `flex-shrink: 0` | Icon crushed on narrow screens | Always add `flex-shrink: 0` |

**Button checklist (every button):**
```
[ ] Text + icon on same vertical axis? (align-items: center)
[ ] Does scale(0.97) active state shift text?
[ ] Equal left/right padding?
[ ] min-height ≥ 44px?
[ ] Icon wrapper flex-shrink: 0?
[ ] white-space: nowrap?
```

---

## 7. MOTION AND MICRO-INTERACTIONS

### 7.1 Animation Decision Framework (emil-design-eng)

**First ask: How often will users see this animation?**

| Frequency | Decision |
|-----------|----------|
| 100+/day (keyboard shortcuts, command palette toggle) | **Never animate** |
| Tens/day (hover effects, list navigation) | Remove or drastically reduce |
| Occasional (modals, drawers, toasts) | Standard animation |
| Rare/first-time (onboarding, celebrations) | Can add delight |

**Never animate keyboard-initiated actions.**

### 7.2 Easing Rules (emil-design-eng)

| Situation | Easing |
|-----------|--------|
| Enter/exit | **ease-out** (starts fast, feels responsive) |
| On-screen movement/morph | ease-in-out |
| Hover/color change | ease |
| Constant motion (marquee, progress) | linear |

**Never use ease-in for UI animations.** It starts slow, making the interface feel sluggish.

Custom easings (built-in CSS easings are too weak):
```css
--ease-out: cubic-bezier(0.23, 1, 0.32, 1);
--ease-in-out: cubic-bezier(0.77, 0, 0.175, 1);
--ease-drawer: cubic-bezier(0.32, 0.72, 0, 1); /* iOS-like */
```

### 7.3 Duration Hierarchy (emil-design-eng)

| Element | Duration |
|---------|----------|
| Button press | 100-160ms |
| Tooltip, small popover | 125-200ms |
| Dropdown, select | 150-250ms |
| Modal, drawer | 200-500ms |
| **Rule:** UI animations under 300ms |

### 7.4 Spring > Duration (emil-design-eng)
- Drag + momentum → spring
- Elements that should feel "alive" → spring
- Interruptible gestures → spring
- Mouse-tracking → `useSpring` (never track continuous values with `useState`)

### 7.5 Enter/Exit Formula (make-interfaces-feel-better)
- **Enter:** opacity + small translateY + optional blur
- **Exit:** shorter, quieter (150ms)
- **Icon swap:** opacity + scale + blur cross-fade
- **Press:** `scale(0.96)`, provide a way to disable if distracting

### 7.6 CSS Transition > Keyframe (make-interfaces-feel-better)
Use CSS transitions for interactive states — they can retarget if the user changes
intent mid-motion. Save keyframes for staged one-shot entrances.

---

## 8. PERFORMANCE

### 8.1 Render Pipeline (fixing-motion-performance)

| Layer | Properties | Cost |
|-------|-----------|------|
| Composite | transform, opacity | Cheapest |
| Paint | color, border, gradient, mask, filter | Medium |
| Layout | size, position, flow, grid, flex | Most expensive |

### 8.2 Never Do
- Interleave layout reads and writes in the same frame
- Continuously animate layout on large surfaces
- Drive animation from scroll events — use **Scroll/View Timeline** or **IntersectionObserver**
- Track continuous values (mouse, scroll) with `useState` — use Motion's `useMotionValue`
- `will-change` only for first-frame stutter, temporary and surgical

### 8.3 FLIP Technique
When layout change is unavoidable: measure → change → calculate inverse → animate via transform.
Never call `getBoundingClientRect()` inside the animation loop.

### 8.4 Blur
- ≤ 8px, short, one-time only
- Never continuous, never large surfaces
- Only on fixed/sticky elements

### 8.5 GPU-Safe (soft-skill)
Only animate `transform` and `opacity`. Never `top`, `left`, `width`, `height`.
`will-change: transform` only during active animation.

---

## 9. ACCESSIBILITY (WCAG 2.2 AA)

### 9.1 Priority Order (fixing-accessibility)
1. **Accessible names** (critical) — every control must have a name, icon-only = aria-label
2. **Keyboard** (critical) — Tab reachable, Escape closable, tabindex > 0 forbidden
3. **Focus & dialogs** (critical) — trap, restore, initial focus
4. **Semantics** (high) — native > role hack; no heading level skips
5. **Forms & errors** (high) — aria-describedby, aria-invalid
6. **Announcements** (medium) — aria-live, aria-busy
7. **Contrast** (medium) — hover must also have keyboard equivalent
8. **Motion** (low) — prefers-reduced-motion
9. **Tool boundaries** (critical) — if native solves it, don't add aria; don't migrate UI libraries

### 9.2 Checklist (Every Component)
- [ ] Keyboard: Tab, Enter, Escape, Arrows
- [ ] Focus: visible outline (never `outline: none` alone)
- [ ] ARIA: correct roles
- [ ] Contrast: AA minimum
- [ ] Screen reader: alt text, aria-label
- [ ] Form: every input has a label, error states announced
- [ ] Color: meaning never conveyed by color alone

---

## 10. EDGE CASES — Every State Designed

```
✅ Ideal (populated)
🔄 Loading (skeleton, not spinner)
📭 Empty (meaningful + action)
❌ Error (what happened + what to do)
🚫 Disabled (why + how to enable)
📱 Responsive (no break at 320px)
🌍 i18n ready (30% expansion room)
```

**Specific rules:**
- `h-dvh` — not `h-screen` (mobile address bar safe)
- `safe-area-inset` for fixed elements
- Never block paste in inputs/textareas
- Empty states need ONE clear action
- AlertDialog for destructive operations
- Never use `useEffect` as render logic

---

## 11. BANNED AI PATTERNS

If you're about to write any of these, STOP and restructure:

| Pattern | Source |
|---------|--------|
| Cream/sand body bg (OKLCH L 0.84-0.97, C<0.06, hue 40-100) | impeccable |
| `border-left/right > 1px` colored stripe | impeccable |
| `background-clip: text` gradient | impeccable |
| Glassmorphism as default | impeccable |
| Hero-metric (big number + label + stats) | impeccable |
| Identical card grids | impeccable |
| Tiny uppercase eyebrow on every section | impeccable |
| 01/02/03 numbered section markers | impeccable |
| Text overflow (clamp + narrow grid) | impeccable |
| `<img>` animation on hover (group-hover:scale) | impeccable |
| Gradient (especially purple/multicolor) | baseline-ui |
| Glow effects as primary affordance | baseline-ui |
| `transition: all` | make-interfaces-feel-better |
| `will-change: all` | make-interfaces-feel-better |
| Inter, Roboto, Arial fonts (premium projects) | soft-skill |
| `ease-in` for UI animations | emil-design-eng |
| Keyboard action animations | emil-design-eng |
| `useState` for continuous value tracking | taste-skill |
| Arbitrary `z-[999]` z-index | baseline-ui + soft-skill |

---

## 12. RESPONSIVE DESIGN — Mobile First

Mobile is 60%+ of traffic. Responsive isn't added later — **it IS the design.**

### 12.1 Breakpoint Strategy

```css
/* Mobile-first: base styles are for mobile */
/* Tablet: 640px+ */
@media (min-width: 640px) { ... }
/* Desktop: 1024px+ */
@media (min-width: 1024px) { ... }
/* Wide: 1280px+ (optional) */
@media (min-width: 1280px) { ... }
```

### 12.2 Per-Component Checks

| Point | Mobile | Tablet | Desktop |
|-------|--------|--------|---------|
| **Grid** | 1 column | 2 column (or per card count) | Per Section 5.5 table |
| **Font** | -10% smaller (clamp handles this) | Normal | Normal |
| **Padding** | `px-4` → `px-6` → `px-8` | Medium | Wide |
| **Nav** | Hamburger/bottom | Fixed/selected | Selected |
| **Hero** | Full width, smaller text | Medium | Full design |
| **Touch** | 44px+ target, 8px+ gap | 44px+ | 44px+ |
| **Images** | Small, lazy | Medium | Full quality |

### 12.3 Never on Mobile

| Mistake | Result | Fix |
|---------|--------|-----|
| `h-screen` | iOS Safari address bar overflow | `min-h-dvh` or `min-h-[100dvh]` |
| Horizontal scroll | Content overflow, user scrolls sideways | `overflow-x-hidden` + find the real cause |
| `hover` for critical interaction | No hover on mobile, functionality lost | `click/tap` primary, hover enhancement only |
| Fixed `width: 1200px` | Horizontal scroll on mobile | `max-width` + `width: 100%` |
| `zoom` blocking | Accessibility violation | `user-scalable=yes` (default) |
| Forcing asymmetric grid on mobile | 2-column asymmetry becomes meaningless in 1 column | Mobile: `grid-template-columns: 1fr` |
| `font-size: clamp(4rem, 10vw, 9rem)` headings | Still too big on mobile | Separate mobile clamp: `clamp(2.5rem, 12vw, 4rem)` |

### 12.4 Test Commands

Mentally test every page at these resolutions:
```
[ ] 375px  (iPhone SE)  — everything visible? any horizontal scroll?
[ ] 768px  (iPad mini)  — correct grid column count?
[ ] 1024px (iPad Pro)   — desktop transition smooth?
[ ] 1440px (MacBook)    — content not too stretched?
```

---

## 13. TECHNOLOGY CHOICES

| Purpose | Preference |
|---------|-----------|
| Styling | Tailwind v4 (default) |
| Animation | Motion (`motion/react`), GSAP (complex) |
| Color | OKLCH, fallback HSL |
| Icons | Phosphor, Lucide, Remix Line (ultra-light) |
| Font | next/font or self-host + font-display:swap |
| Forms | react-hook-form + zod |
| Accessibility | Radix UI, Base UI, React Aria |
| State | Local useState/useReducer; global: Zustand/Jotai |

---

## 14. DESIGN SYSTEM MAP (taste-skill)

If the brief points to a design system, use the **official package** — don't
hand-write its CSS:

| Brief | System |
|-------|--------|
| Microsoft / enterprise SaaS | @fluentui/react-components |
| Google-ish / Material | @material/web + M3 tokens |
| IBM-style B2B | @carbon/react |
| GitHub-style devtool | @primer/css |
| Public-sector UK | govuk-frontend |
| US public-sector | uswds |
| Modern React foundation | @radix-ui/themes |
| Own components + SaaS | shadcn/ui |
| Indie / small team | Tailwind v4 |

**One system per project.** Never mix Fluent + Carbon.

---

## 15. OUTPUT DISCIPLINE

- Never `// ... more items`, `{/* TODO */}`, truncated code
- Always production-ready, all imports, all styles
- All states: loading, empty, error, disabled
- Responsive: tested at 320px, 768px, 1024px, 1440px
- All reference paths must be absolute

---

## 16. SUMMARY CHECKLIST

Before writing code:
1. [ ] Design Read done?
2. [ ] 3 dials (VARIANCE/MOTION/DENSITY) set?
3. [ ] Color strategy chosen (Restrained/Committed/Full/Drenched)?
4. [ ] How often will users see this? (Animation decision)

After writing code:
5. [ ] Any banned patterns present?
6. [ ] Spacing on 4px scale?
7. [ ] Contrast meets AA?
8. [ ] Keyboard navigable?
9. [ ] Any `transition: all` or `will-change: all`?
10. [ ] Any layout animation (width/height/top/left)?
11. [ ] `h-dvh` used instead of `h-screen`?
12. [ ] Does it break at 320px?

---

## 17. CONTRAST & READABILITY — Improving LLM Output

> **Core problem:** AI models optimize for "looks good," not "works for everyone."
> WebAIM 2024: **95.9% of web pages have WCAG failures.** AI learns from this
> data — it copies the same mistakes.

### 17.1 AI's Most Common Contrast Mistakes

| Mistake | Example | Actual Ratio | Required |
|---------|---------|-------------|----------|
| **Light gray text / white BG** | `#999` on `#fff` | ~2.8:1 | 4.5:1 |
| **Medium gray text** | `#666` on `#fff` | ~5.2:1 ✅ | — (this passes) |
| **Pale gray text** | `#999` on `#f5f5f5` | ~2.1:1 | 4.5:1 |
| **Blue link / dark BG** | `#007bff` on `#1a1a1a` | ~2.1:1 | 4.5:1 |
| **Accent color as body text** | Orange on light | ~2.8:1 | 4.5:1 |
| **Dark mode gray text** | Brown/beige on dark | ~2-3:1 | 4.5:1 |

**Most common failure:** AI thinks light gray text looks "clean" and "modern."
In reality, 2:1 contrast is less than half of WCAG AA.

### 17.2 Why AI Misses Contrast

1. **Training data isn't accessible.** Millions of web pages have the same mistakes.
   AI thinks "this is how it should look."
2. **AI doesn't calculate contrast.** It doesn't do math when picking colors — it
   does probabilistic pattern matching.
3. **No color blindness simulation.** 8% of men, 0.5% of women are color blind.
   ~4000 users per 100K see the interface differently.
4. **Dark mode is an afterthought.** Colors chosen for light mode may not work in dark.

### 17.3 Hard Rules (Prompt Level)

Apply these to every frontend task:

```
1. Body text: minimum 16px, line-height ≥ 1.5, contrast ≥ 4.5:1
2. Large text (≥18px bold or ≥24px): contrast ≥ 3:1
3. Placeholder text also needs 4.5:1 (muted-gray default fails)
4. Text never below 12px (for body)
5. NEVER use gray text + white BG combination.
   "Clean" looking light gray = inaccessible.
6. NEVER use color as the ONLY meaning carrier.
   Error/success must always be supported with icon + text.
7. NEVER use brown/beige text in dark mode.
   This is AI's most common dark mode mistake.
8. NEVER remove focus ring. `outline: none` alone = forbidden.
```

### 17.4 Prompt Engineering: Getting Accessible Output from AI

When requesting UI from AI, always include these specifications:

> "Generate a [component] with: 16px minimum text size, 4.5:1 contrast
> ratios on all text, proper semantic HTML, 44px minimum touch targets,
> visible focus indicators, and no color-only state indicators."

### 17.5 Self-Audit Commands

After generating output, the AI should self-check:

```
1. [ ] All text 16px or above?
2. [ ] Line-height ≥ 1.5 for body?
3. [ ] Are any 2+ text/BG pairs below 4.5:1? If yes, FIX.
4. [ ] Focus ring visible? (outline: none alone?)
5. [ ] Any meaning conveyed by color alone? If yes, add icon/text.
6. [ ] Touch targets at least 44×44px?
7. [ ] Dark mode text not brown/beige?
8. [ ] Any `transition: all` or `will-change: all`?
```

### 17.6 Color Roles and Usage Matrix

Every color must have a role. Using a color outside its role = error:

| Role | Where TO use | Where NOT to use |
|------|-------------|-----------------|
| **Ink** (text) | Body, heading, label | — (only use: text) |
| **Background** | Page/card background | — |
| **Accent** | CTA button, link, highlight | **NEVER as body text** |
| **Muted** | Secondary text, caption | **NEVER as body text** (contrast fails) |
| **Border** | Dividers | As text (contrast too low) |

### 17.7 Quick Contrast Test Formula (When No Tool Available)

If using OKLCH, rough approximation:
- **L value difference ≥ 40** → generally passes 4.5:1
- **L difference < 30** → almost certainly FAILS
- Light mode darkest text: L = 20-35
- Dark mode lightest text: L = 85-95
- For muted text: target L difference ≥ 50 (for AAA)

> **Remember:** 80% of the gray text AI calls "beautiful" fails WCAG.
> The moment you see `#999999` as body text, fix it.

---

## 18. STYLE AND THEME CATALOG (30 Themes)

A style library that guides the agent when the user says "make it look good"
without specifying a visual direction. If the agent can't infer from the brief,
offer the user 2-3 closest styles from this catalog.

### 18.1 Dark / Technology

**1. Dark Terminal** — Raw, CRT hacker aesthetic. `#0A0A0A` bg, `#4AF626` green phosphor, monospace font. Dev tools, CLI docs, security products.

**2. Deep Tech / OLED** — Premium black, neon accents. `#040308` bg, `#C44DFF` accent. Grotesk display. AI/ML, game studios, devtool landing.

**3. Cyberpunk / Neon Noir** — Rainy streets, synthetic. `#0D0221` bg, magenta+cyan. Square sans. Games, music, Web3.

**4. Graphite / Monochrome Dark** — Serious, corporate. 12 gray tones + single accent. Humanist sans. Professional tools, B2B SaaS.

### 18.2 Light / Clean

**5. Editorial Minimal** — Magazine page, typography first. `#FDFBF7` cream, serif heading. Blog, portfolio, content.

**6. Swiss Modern** — Graphic design, grid, objective. `#FFFFFF` + red/blue accent. Neo-grotesk. Architecture, design studio.

**7. Soft Structuralism** — Silver-gray, airy. `#F5F5F7` + soft blue. SF Pro. Consumer, health, Apple-esque.

**8. Clean SaaS** — Professional, trustworthy. `#FFFFFF` + `#2563EB`. Geometric sans. SaaS landing, B2B.

### 18.3 Warm / Organic

**9. Editorial Luxury** — Boutique hotel lobby. `#FDF8F0` cream, `#2D1B0E` espresso, `#C4A265` gold. Luxury real estate, fashion.

**10. Earth / Natural** — Organic, earth tones. `#F4F1EA` + green/terracotta. Serif + rounded sans. Sustainability, outdoor.

**11. Mediterranean / Warm** — Mediterranean, stone, olive. `#FEF9F0` + dark green + earth. Restaurant, travel.

### 18.4 Bold / Experimental

**12. Brutalist** — Raw concrete, uncompromising. `#F4F4F0` newsprint, `#E61919` red. Heavy grotesk, border-radius:0. Portfolio, experimental.

**13. Bento Grid** — Apple keynote, modular. Asymmetric CSS Grid. SF Pro. Product showcase, feature display.

**14. Memphis / Playful** — 80s geometry, fun. Multiple high-contrast colors. Rounded display font. Children, events.

**15. Z-Axis Cascade** — 3D feel, layered. Overlapping cards, rotated. Portfolio, agency.

### 18.5 Glass / Light

**16. Ethereal Glass** — Vantablack + glass. `#050505` + `backdrop-blur-2xl`. AI/tech SaaS.

**17. Aurora / Mesh Gradient** — Northern lights, dreamy. Purple/blue/green gradients. Creative tools, music.

**18. Frosted Glass / Light** — Bright frosted glass. `#F0F0F5` + blur. iOS app landing, modern dashboard.

### 18.6 Retro / Nostalgic

**19. Vaporwave / Synthwave** — 80s Miami. Pink/purple/cyan. Outrun font. Music, games, festivals.

**20. Y2K / Web 1.0** — 2000s internet. Web-safe palette, pixel font, marquee. Nostalgia, ironic.

**21. Grunge / Punk** — Concert poster, photocopy. Paper tone + toner black + spray red. Music, streetwear.

### 18.7 Corporate / Trust

**22. Trust-First / Public Sector** — Accessible, official. Gov blue `#1D70B8`. System font. Public sector, health, banking.

**23. Corporate / Enterprise** — Large company. `#003366` + limited red accent. Enterprise SaaS, investor.

**24. Financial / Fintech** — Trust + data. `#0F1923` + `#00D4AA`. Mono numbers. Banking, crypto.

### 18.8 Creative / Artistic

**25. Editorial Split** — Split page. w-1/2 text + w-1/2 visual. Portfolio, photography.

**26. Magazine / Editorial** — Vogue/NYT digital. Didot/Bodoni serif. Publishing, long-form.

**27. Kinetic Typography** — Moving type. Scroll-driven, variable font. Brand storytelling.

### 18.9 Mobile / App

**28. Mobile-First / App Shell** — Native app feel. iOS HIG / Material. Mobile landing.

**29. Dashboard / Data-Dense** — Data cockpit. Dark bg, semantic colors. Analytics, monitoring.

**30. Onboarding / Welcome Flow** — Warm welcome. Progress bar, illustration. App onboarding.

---

### 18.10 Style Selection Algorithm

| Signal | Style # |
|--------|---------|
| "dark / night / dark mode" | 1, 2, 3, 4, 16 |
| "modern / clean / simple" | 5, 6, 7, 8 |
| "warm / friendly / organic" | 9, 10, 11 |
| "bold / different / experimental" | 12, 13, 14, 15 |
| "premium / luxury / expensive" | 9, 17, 18 |
| "retro / old / nostalgic" | 19, 20, 21 |
| "corporate / serious / trustworthy" | 22, 23, 24 |
| "creative / artistic / portfolio" | 25, 26, 27 |
| "mobile / app" | 28, 29, 30 |
| "AI / tech / software" | 2, 8, 16 |
| "game / entertainment" | 3, 14, 19 |

**If the user specifies nothing:** Select by product type.
SaaS → 8, Portfolio → 5, Game → 2, Landing → 2 or 8, Dashboard → 29.

---

## Source Skills

This skill is based on complete content analysis of these 9 SKILL.md files:

| Skill | Author | Key Contribution |
|-------|--------|-----------------|
| taste-skill | Leonxlnx | 3-dial system, brief inference, design system map |
| soft-skill | Leonxlnx | Double-Bezel, variance engine, banned fonts/icons |
| brutalist-skill | Leonxlnx | Swiss Industrial + Tactical Telemetry aesthetics |
| impeccable | pbakaus | Color strategy, absolute bans, anti-AI patterns |
| baseline-ui | Ibelick | Tailwind enforcement, animation/performance constraints |
| emil-design-eng | emilkowalski | Animation decision framework, spring physics, frequency-based |
| make-interfaces-feel-better | jakubkrehel | Micro-polish: concentric radius, optical alignment, hit areas |
| fixing-accessibility | Ibelick | WCAG priority-ordered rules |
| fixing-motion-performance | Ibelick | Render pipeline, FLIP, blur constraints |

The remaining 100 skills were framework-specific (Vue, React, Next.js, Three.js,
Svelte), too narrow (Slidev, tsdown, Pinia), or variations of the above, and were
not analyzed separately.
