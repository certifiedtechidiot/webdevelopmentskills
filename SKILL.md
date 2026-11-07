---
name: webdevelopment
description: >-
  Unified all-in-one web development skill combining Get Shit Done (GSD spec-driven engineering, phase planning, execution loop, state tracking), Hallmark (anti-AI-slop design system, strict design floor, material themes, sloplint), and AI Design Skill (conversion architecture, landing page strategy, typography, spacing, UI polish). Activates automatically whenever building, designing, refactoring, auditing, styling, or shipping web projects, websites, applications, components, or landing pages, or when the user invokes /webdevelopment.
---

# Unified Web Development Engine (GSD + Hallmark + AI Design)

This skill brings together the top three development frameworks into a single, cohesive workflow:
1. **Get Shit Done (GSD)** — Phased, spec-driven engineering, execution verification, and project memory.
2. **Hallmark** — The strict anti-AI-slop design floor, material themes, and `sloplint` linting.
3. **AI Design Skill** — High-converting page structure, conversion copywriting, typography scale, and layout rhythm.

When this skill is invoked via `/webdevelopment` (or during web development tasks), execute all 3 frameworks in unison.

---

## The 3 Integrated Pillars

### 1. GSD Execution Loop (Engineering & Project Memory)
Maintain persistent project context in `.planning/` to eliminate context degradation over long coding sessions:
* **`.planning/PROJECT.md`** — Core project scope, offer, target users, and technical stack.
* **`.planning/ROADMAP.md`** — Milestones, phases, and deliverable checkboxes.
* **`.planning/STATE.md`** — Current progress, decisions made, pending items, and active blockers.
* **Phase Loop**: *Intake & Spec → Plan → Execute (Hero/Core Anchor First) → Verify & Test → Ship*.

### 2. The Hallmark Design Floor (Non-Negotiable Craft Standards)
Every interface generated must look custom-crafted, never generic or machine-made:
1. **Tokenized Variables**: Every color, font, and radius MUST be declared as CSS tokens at `:root` or design system theme variables. Zero un-tokenized literal hex values or inline `font-family` declarations in components.
2. **Smooth Transitions**: Never `transition: all`. Never animate `width`, `height`, `top`, or `left`. Animate only `transform` and `opacity`.
3. **Clean Typography**: Never one italic word inside a roman heading. Never all-caps or small-caps for body labels or eyebrows.
4. **No Horizontal Spills**: Apply `overflow-x: clip` to both `html` and `body` (never `hidden`, never `100vw`).
5. **Instant Accessibility**: Every button and interactive control must feature instantaneous, high-visibility `:focus-visible` outlines. Respect `prefers-reduced-motion: reduce`. Content must remain legible if scripting is disabled.
6. **No AI Clichés**:
   * Never use purple-to-blue gradients.
   * Never nest cards inside cards.
   * Never use emojis as feature icons.
   * Never generate fake metrics, invented testimonials, or decorative status dots.
7. **Hero Viewport Standard**: The hero's headline, single-sentence summary, and primary CTA must fit in `1280x800` without scrolling (~80 words total).
8. **Automated Sloplint**: Run `node <skill-dir>/scripts/sloplint.mjs <file> --render` to audit generated HTML/CSS. Fix any `FAIL` flags before handing back.

### 3. AI Design & Conversion Architecture (Strategy & Spacing)
1. **The Core Formula**: One Offer → One Audience → One Primary Action.
2. **Intake Strategy**:
   * Clarify the single primary action (e.g. signup, demo, buy, waitlist).
   * Identify the target ICP and top objections to tackle.
3. **Harmonious Typography**:
   * Snap all font sizes to the standard type scale (`text-xs` through `text-6xl`).
   * Apply negative letter-spacing (`tracking-tight`) on display headers and positive letter-spacing on small caps/tags.
   * Use `text-wrap: balance` on headlines and `text-wrap: pretty` on body copy.
4. **Spacing Grid**: Strict 4px/8px scale (`gap-2`, `gap-4`, `p-6`, `py-12`, `py-20`).

---

## Step-by-Step Workflow

```
[Step 1: Intake & Spec]        (GSD + AI Design Strategy)
          │
[Step 2: Token Architecture]   (Hallmark Floor + Tokens)
          │
[Step 3: Build Hero & Anchor]  (Hallmark + AI Design)
          │
[Step 4: Phased Execution]     (GSD Phased Development)
          │
[Step 5: Anti-Slop Audit]      (Hallmark sloplint.mjs + Tests)
          │
[Step 6: State & Delivery]     (GSD STATE.md + Ship)
```

### Step 1: Intake & Scope Setup
* Check if `.planning/` exists. If not, initialize `.planning/PROJECT.md` and `.planning/STATE.md`.
* For new builds: confirm primary goal, user audience, and brand feel in a single concise batch.
* For redesigns: audit the existing page against the checklist in [`./references/ai-design/redesign-audit.md`](./references/ai-design/redesign-audit.md), then upgrade without altering underlying functionality.

### Step 2: Establish the Visual Tokens
* Declare the project's token palette in `:root` (or Tailwind theme variables):
  - Primary, neutral, background, surface, and accent tokens.
  - Distinctive typography pairings (e.g., editorial serif + clean grotesque, or geometric sans + monospace accents).
  - Standardized border-radius tokens (`--radius-sm`, `--radius-md`, `--radius-lg`).

### Step 3: Implement the Hero & Core Anchor
* Build the primary anchor or hero section first.
* Verify it meets the 1280x800 viewport requirement, has tight conversion-focused copy, and contains no AI slop clichés.

### Step 4: Phased Execution of Features
* Implement subsequent sections (features, proof, pricing, interactive components) incrementally.
* Ensure all interactive states (`:hover`, `:active`, `:focus-visible`) are distinct and fluid.

### Step 5: Automated Sloplint & Testing
* Run `node ./scripts/sloplint.mjs <target>` to catch layout or style regressions.
* Run project test suites or build commands (`npm run build`, `npm test`) to guarantee zero compile or runtime warnings.

### Step 6: Update State & Ship
* Log changes and phase completions in `.planning/STATE.md`.
* Deliver clean, production-ready code to the user with a concise summary of choices made.

---

## Reference Guides

* **Hallmark Design Themes**: [`./references/hallmark/themes.md`](./references/hallmark/themes.md)
* **Hallmark Quality Gates**: [`./references/hallmark/gates.md`](./references/hallmark/gates.md)
* **Hallmark Layout & Craft**: [`./references/hallmark/layout.md`](./references/hallmark/layout.md) and [`./references/hallmark/craft.md`](./references/hallmark/craft.md)
* **AI Design Landing Page Guide**: [`./references/ai-design/landing-page-design.md`](./references/ai-design/landing-page-design.md)
* **AI Design Redesign Audit**: [`./references/ai-design/redesign-audit.md`](./references/ai-design/redesign-audit.md)
* **GSD Workflow Engine**: [`./references/gsd/`](./references/gsd/)
* **Sloplint Linter**: [`./scripts/sloplint.mjs`](./scripts/sloplint.mjs)
