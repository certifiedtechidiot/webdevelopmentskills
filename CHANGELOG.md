# Changelog

All notable changes to the `webdevelopment` skill package will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.3.0] — 2026-11-07

### Added
- **Activation Tiers**: Added task-weight classification at the entry point of the pipeline:
  - **Tier 1 (Component)**: Activates Hallmark + Impeccable playbooks only (skips heavy GSD project memory).
  - **Tier 2 (Feature/Section)**: Activates Hallmark + AI Design + Taste 2.5 + Impeccable.
  - **Tier 3 (Full Build / Redesign)**: Full 6-pillar pipeline with `.planning/` project memory and automated `sloplint.mjs` verification.
- **Conflict Resolution Hierarchy**: Explicit 6-tier precedence system governing conflicts between speed, craft, and conversion:
  1. Impeccable (Craft & Accessibility floor)
  2. Hallmark (Anti-slop & Token discipline)
  3. AI Design Skill (Conversion & Layout grid)
  4. Taste Skill 2.5 (Screen rhythm & Visual realism)
  5. OpenDesign (Brand design system tokens)
  6. GSD (Velocity & Execution loop)
- **Anti-Slop Blacklist**: Strict, testable "DO NOT" rules in `SKILL.md` banning purple-to-blue gradients, nested cards, emoji icons, fake metrics, `transition: all`, and layout animations.
- **Proof & Reference Gallery**:
  - `references/before-after/saas-card-before.html` vs. `saas-card-after.html`
  - `references/before-after/hero-section-before.html` vs. `hero-section-after.html`
  - `references/hallmark-violations.md` (annotated visual breakdown)
  - `references/sloplint-output-example.txt` (sample terminal run)
- **Verification Scripts Documentation**: Created `scripts/README.md` covering rule categories, CLI flags, exit codes, and extension guides for `sloplint.mjs` and `consistency.mjs`.
- **Runtime Verification Commands**: Added `/webdevelopment ping` for instant environment validation and `/webdevelopment demo` for generating canonical reference deliverables.

### Changed
- Standardized `plugin.json` `suggestedPrompts` to 3 items to adhere strictly to runtime limits.
- Upgraded package version across `plugin.json`, `package.json`, and `SKILL.md`.

---

## [1.1.0] — 2026-11-07

### Added
- **Taste Skill (tasteskill 2.5)**: Figma-grade visual realism, screen-height rhythm, real product UI, micro-animations, and trade-specific shader moments.
- **Impeccable (v4.8)**: Director-level UI/UX craft, 4 surface modes (*Persuade, Operate, Read, Experience*), and 19 specialized playbooks.
- **OpenDesign**: 100+ production brand design systems (Stripe, Linear, Vercel, Apple, GitHub, Supabase, etc.) and universal craft rules.

---

## [1.0.0] — 2026-11-07

### Added
- Initial unified release combining:
  - **Get Shit Done (GSD)**: Spec-driven engineering, phase planning, execution loop, state tracking.
  - **Hallmark**: Anti-AI-slop design system, strict design floor, material themes, and `sloplint.mjs`.
  - **AI Design Skill**: Conversion architecture, landing page strategy, typography scale, and layout polish.

---

## Versioning & Breaking Changes Policy

- **MAJOR (`x.0.0`)**: Any breaking change that removes an integrated pillar, deprecates a primary command, changes core design token defaults, or modifies the conflict resolution hierarchy.
- **MINOR (`0.x.0`)**: Additive enhancements, such as new playbooks, additional brand design systems in OpenDesign, new linter checks in `sloplint.mjs`, or updated reference galleries.
- **PATCH (`0.0.x`)**: Bug fixes, typo corrections, regex optimizations, and performance improvements in scripts.
