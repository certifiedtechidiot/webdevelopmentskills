---
name: open-design
description: >-
  OpenDesign multi-brand design system catalogue and craft framework. Gives agents instant access to 100+ battle-tested industry design systems (Stripe, Linear, Vercel, Apple, Airbnb, GitHub, Supabase, Notion, Figma, Raycast, Resend, PostHog, etc.) with exact tokens, type scales, multi-layer elevation shadows, and universal craft rules (accessibility, laws of UX, animation discipline, state coverage). Use whenever the user asks to style like a specific company, build a design system, choose brand tokens, or enforce universal design craft.
version: 1.0.0
---

# OpenDesign: Multi-Brand Design System & Craft Framework

OpenDesign provides a comprehensive catalogue of over 100 production design systems and universal craft guidelines. It enables agents to generate, adopt, or adapt battle-tested visual identities with exact color palettes, typography scales, OpenType features, elevation systems, and component conventions.

---

## 1. 100+ Brand Design Systems Catalogue

Inspect the corresponding `design-systems/<brand>/DESIGN.md` for the exact specifications:

| Category | Available Brand Design Systems |
| :--- | :--- |
| **Fintech & Infrastructure** | `stripe`, `linear-app`, `revolut`, `wise`, `coinbase`, `kraken`, `binance`, `trading-terminal` |
| **Developer Tools & Cloud** | `vercel`, `github`, `supabase`, `cloudflare-kumo`, `hashicorp`, `posthog`, `sentry`, `mongodb`, `clickhouse`, `warp` |
| **AI & Frontiers** | `openai`, `claude`, `x-ai`, `perplexity`, `together-ai`, `mistral-ai`, `cohere`, `huggingface`, `replicate`, `runwayml` |
| **Productivity & Workspace** | `notion`, `figma`, `raycast`, `resend`, `loom`, `intercom`, `slack`, `miro`, `airtable`, `cal`, `superhuman` |
| **Editorial & Minimal** | `editorial`, `theverge`, `wired`, `minimal`, `atelier-zero`, `warm-editorial`, `publication`, `paper` |
| **Expressive & Aesthetics** | `brutalism`, `neobrutalism`, `glassmorphism`, `claymorphism`, `neumorphism`, `dithered`, `retro`, `cosmic` |
| **Consumer & Automotive** | `apple`, `airbnb`, `spotify`, `nike`, `tesla`, `spacex`, `bmw`, `ferrari`, `lamborghini`, `canva` |

### Using a Brand System
1. Locate the requested brand under `./design-systems/<brand>/DESIGN.md`.
2. Extract the exact token definitions:
   - Primary, dark/brand, neutral, and accent hex values.
   - Typography pairings and OpenType feature sets (e.g., `ss01`, `tnum`).
   - Signature elevation models (e.g., Stripe's blue-tinted multi-layer shadows, Linear's crisp 1px borders).
3. Inject the tokens into `:root` or design system CSS variables.

---

## 2. Universal Craft Rules (`craft/`)

Before finalizing any frontend interface, apply the non-negotiable guidelines from `craft/`:

* **Anti-AI-Slop (`craft/anti-ai-slop.md`)**:
  - Eliminate purple-blue gradients, floating cards, decorative dots, and meaningless emojis.
  - Enforce intentional typography, authentic photography, and purpose-driven interaction.
* **Accessibility Baseline (`craft/accessibility-baseline.md`)**:
  - WCAG AA contrast compliance (`4.5:1` normal text, `3:1` large text/UI components).
  - Unbroken keyboard navigation, visible `:focus-visible` rings, screen reader landmarks.
* **Animation Discipline (`craft/animation-discipline.md`)**:
  - Animate only composite properties (`transform`, `opacity`). Never animate layout dimensions (`width`, `height`, `margin`).
  - Standard duration scale: `150ms` (snappy micro-feedback), `250ms` (component shifts), `400ms` (page transitions).
  - Respect `prefers-reduced-motion: reduce`.
* **Laws of UX (`craft/laws-of-ux.md`)**:
  - *Fitts's Law*: Make primary action targets large and easily clickable.
  - *Hick's Law*: Minimize choices per screen (One Offer → One Primary Action).
  - *Jakob's Law*: Familiar mental models for common flows (e.g. login, settings, table sorting).
* **State Coverage (`craft/state-coverage.md`)**:
  - Every component must have 6 states designed: *Default*, *Hover*, *Active*, *Focus*, *Disabled*, and *Loading*.
* **Typography Hierarchy (`craft/typography-hierarchy.md`)**:
  - Standard type scale from `text-xs` to `text-6xl`.
  - Negative letter-spacing on display headers, positive on microcopy/eyebrows.

---

## 3. Workflow Integration

When designing or refactoring a UI:
1. **Brand Choice**: Ask or detect the brand mood (e.g. "Linear-like dark theme" or "Stripe-like fintech clean").
2. **Token Extraction**: Read `design-systems/<brand>/DESIGN.md` and declare all variables in `:root`.
3. **Layout & Spacing**: Apply strict 4px/8px grid and screen-height viewport rhythms.
4. **Craft Verification**: Run through the `craft/` guidelines for accessibility, animation, and state coverage before shipping.
