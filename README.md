# ⚡ Web Development Skills (`/webdevelopment`)

> **The Unified 4-in-1 Master Skill for AI Coding Assistants**  
> Combines **Get Shit Done (GSD)**, **Hallmark (Anti-AI-Slop)**, **AI Design Skill**, and **Taste Skill (tasteskill 2.5)** into one cohesive command.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Runtime: Universal](https://img.shields.io/badge/Runtime-Antigravity%20%7C%20Claude%20Code%20%7C%20Cursor%20%7C%20Codex-brightgreen.svg)]()

Instead of juggling and remembering separate slash commands (`/gsd-new-project`, `/hallmark`, `/landing-page-design`, `/taste`, `/sloplint`, etc.), **`/webdevelopment`** triggers all four frameworks simultaneously in an automated, disciplined loop.

---

## 🌟 The 4 Integrated Pillars

```
                     ┌────────────────────────────────────────────────────────┐
                     │               /webdevelopment Pipeline                 │
                     └───────────────────────────┬────────────────────────────┘
                                                 │
            ┌───────────────────┬────────────────┴───────────────────┬───────────────────┐
            ▼                   ▼                                    ▼                   ▼
   ┌─────────────────┐ ┌─────────────────┐                  ┌─────────────────┐ ┌─────────────────┐
   │    GSD Core     │ │ Hallmark Floor  │                  │ AI Design Skill │ │   Taste Skill   │
   ├─────────────────┤ ├─────────────────┤                  ├─────────────────┤ ├─────────────────┤
   │ • Spec build    │ │ • Anti-AI-slop  │                  │ • 1 Offer/Action│ │ • figma & x.ai  │
   │ • .planning/ mem│ │ • :root tokens  │                  │ • Conversion UX │ │ • Screen rhythm │
   │ • Phase loop    │ │ • Typography    │                  │ • 4px/8px grid  │ │ • Micro-anims   │
   │ • Verification  │ │ • sloplint.mjs  │                  │ • Copy formulas │ │ • Shader moments│
   └─────────────────┘ └─────────────────┘                  └─────────────────┘ └─────────────────┘
```

### 1. 🏗️ Get Shit Done (GSD) — Engineering & State Memory
* **Persistent Project Memory**: Maintains `.planning/` (`PROJECT.md`, `ROADMAP.md`, `STATE.md`). Eliminates context rot across sessions.
* **Disciplined Phase Loop**: *Intake & Spec → Plan → Execute (Hero First) → Verify & Test → Ship*.
* **Never Stalls**: Executes structured milestones with clear verification gates.

### 2. 🎨 Hallmark — The Anti-AI-Slop Design Floor
* **Zero AI Clichés**: No generic purple-to-blue gradients, no cards nested inside cards, no fake metrics, no decorative status dots, no emojis as feature icons.
* **Strict Design Tokens**: All colors, fonts, and radii MUST pass through CSS tokens declared at `:root`.
* **Smooth Craft**: Never `transition: all`. Never animate layout properties (`width`/`height`/`top`/`left`).
* **Hero 1280x800 Viewport Standard**: The hero section (headline, single summary sentence, primary CTA) must fit in a 1280x800 viewport without scrolling (~80 words total).
* **Automated Linting**: Integrated `sloplint.mjs` verifies HTML/CSS to catch generic AI fingerprints before handing code back.

### 3. 🎯 AI Design Skill — Conversion Architecture & UI Polish
* **The Core Formula**: One Offer → One Audience → One Primary Action.
* **Harmonious Typography**: Snapped to the standard type scale (`text-xs` through `text-6xl`), negative tracking on display headers, `text-wrap: balance` on headlines, and `text-wrap: pretty` on body copy.
* **Spacing Grid**: Strict 4px/8px layout rhythm (`gap-2`, `gap-4`, `p-6`, `py-12`, `py-20`).
* **Redesign Diagnostic**: Capable of auditing and upgrading existing websites in place without breaking functionality.

### 4. ✨ Taste Skill 2.5 — The figma.com & x.ai Design Bar
* **Screen-Height Rhythm**: Hero stands alone on the first screen. Subsequent sections are exactly 1 or 2 screens tall at `1440x900`. Equal left/right content margins across all viewports.
* **Real Visuals & No Captions**: Never put captions under images or diagrams (credits live in a single footer line). Real full-color product UI icons (e.g. GitHub, Stripe, Linear) and diagram visuals (hub-and-spoke, processing pipelines).
* **Quiet Micro-Interactions**: Linked cards lift 2px with crisp shadows, photo frames zoom 1.02-1.03x, buttons step on hover and depress on click, card loops cycle seamlessly.
* **Trade Discrimination**: Shader effects and interactive moments reserved strictly for technical subjects (AI, software, gaming, fintech, hardware); physical businesses (cafes, studios, shops) receive authentic photography.

---

## 🚀 Installation

### Option 1: Antigravity
Clone directly into your Antigravity global skills directory:
```bash
git clone https://github.com/certifiedtechidiot/webdevelopmentskills.git ~/.gemini/antigravity/skills/webdevelopment
```

Or add to your `~/.gemini/config/skills.json`:
```json
{
  "entries": [
    {
      "path": "~/.gemini/antigravity/skills"
    }
  ]
}
```

### Option 2: Universal Agents (Claude Code, Cursor, Codex, Windsurf)
Install via the skills CLI:
```bash
npx skills add certifiedtechidiot/webdevelopmentskills -g
```

Or clone into your project's workspace:
```bash
git clone https://github.com/certifiedtechidiot/webdevelopmentskills.git .agents/skills/webdevelopment
```

---

## 💡 How to Use

Simply invoke **`/webdevelopment`** followed by your task:

### 1. Build a New Project or Landing Page
```text
/webdevelopment build a modern SaaS landing page for an AI developer platform
```
*Gathers intake, initializes `.planning/`, generates token palette, builds the 1280x800 hero, applies screen-height rhythm and micro-animations, executes sections, and runs `sloplint`.*

### 2. Redesign an Existing Page
```text
/webdevelopment redesign src/pages/Index.tsx
```
*Scans the existing codebase, diagnoses AI slop anti-patterns, preserves all wiring and state, and upgrades typography and surface tokens in place.*

### 3. Implement New Features or Components
```text
/webdevelopment create an interactive pricing calculator with annual/monthly billing toggle
```
*Builds modular, accessible, zero-slop components adhering to the design tokens and GSD phase standards.*

---

## 📁 Repository Structure

```text
webdevelopmentskills/
├── SKILL.md                          # Root skill entrypoint
├── package.json                      # Metadata
├── README.md                         # Documentation
├── LICENSE                           # MIT License
└── skills/
    ├── webdevelopment/               # The unified master skill
    │   ├── SKILL.md                  # 4-in-1 orchestration rules
    │   ├── scripts/                  # sloplint.mjs, consistency.mjs, etc.
    │   └── references/
    │       ├── taste/                # Taste skill references, cards, motion, moments
    │       ├── hallmark/             # Themes, gates, layout, craft guides
    │       ├── ai-design/            # Landing page guidelines & audit checklists
    │       └── gsd/                  # GSD workflow templates & references
    ├── taste-skill/                  # Standalone Taste Skill (tasteskill 2.5)
    ├── hallmark/                     # Standalone Hallmark skill
    ├── landing-page-design/          # Standalone Landing Page Design skill
    └── redesign-existing-projects/   # Standalone Redesign Audit skill
```

---

## 📄 License

MIT © [certifiedtechidiot](https://github.com/certifiedtechidiot)
