# Hallmark Anti-Patterns & Violations Reference

This reference documents the 8 most common AI design failure modes ("slop") identified by Hallmark and enforced automatically by `sloplint.mjs`.

---

## 1. Generic Purple-to-Blue Gradients & Mesh Glows

### Anti-Pattern
AI models habitually reach for `linear-gradient(135deg, #6366f1, #a855f7, #3b82f6)` as a shortcut for "modern SaaS". This creates identical-looking, cheap interfaces.

### Code Diff
```css
/* ❌ VIOLATION (sloplint FAIL / REFLEX) */
.card {
  background: linear-gradient(135deg, #6366f1 0%, #a855f7 50%, #3b82f6 100%);
  border-radius: 20px;
  box-shadow: 0 10px 40px rgba(168, 85, 247, 0.4);
}

/* ✅ HALLMARK COMPLIANT */
.card {
  background-color: var(--color-bg-surface);
  border: 1px solid var(--color-border-subtle);
  border-radius: var(--radius-md);
  box-shadow: var(--shadow-surface);
}
```

---

## 2. Cards Nested Inside Cards

### Anti-Pattern
Placing container cards inside parent cards (e.g., metric boxes inside a feature card inside a grid container) creates bloated visual weight and confusing visual nesting.

### Code Diff
```html
<!-- ❌ VIOLATION -->
<div class="outer-card">
  <div class="inner-card">
    <div class="nested-stat-box">
      <span>99.9% Faster</span>
    </div>
  </div>
</div>

<!-- ✅ HALLMARK COMPLIANT (Flat layout rhythm with tokenized borders) -->
<article class="card">
  <h2 class="card-title">Instant Branch Isolation</h2>
  <p class="card-description">Clone isolated Postgres staging copies in under 3 seconds.</p>
  <div class="spec-row">
    <span class="spec-label">Provision latency</span>
    <span class="spec-value">&lt; 2.8s median</span>
  </div>
</article>
```

---

## 3. Emojis as Feature Icons

### Anti-Pattern
Using system emojis (`🚀`, `✨`, `⚡`, `🔥`) as iconography instead of professional SVG symbols. Emojis render inconsistently across operating systems and communicate amateurish quality.

### Code Diff
```html
<!-- ❌ VIOLATION -->
<div class="icon">🚀✨</div>

<!-- ✅ HALLMARK COMPLIANT (Crisp inline SVG with aria-hidden) -->
<div class="card-icon" aria-hidden="true">
  <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
    <path d="M12 2v20M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6" />
  </svg>
</div>
```

---

## 4. Fake, Unverifiable Metrics

### Anti-Pattern
Copy filled with arbitrary rounded metrics like "99.9% faster", "Trusted by 10,000+ teams", or "100x productivity".

### Directives
- Replace generic bragging with concrete technical capability.
- Show actual API signatures, CLI commands, benchmark latencies, or workflow states.
- If no real customer count exists, omit social proof metrics entirely.

---

## 5. `transition: all` & Layout Dimension Animations

### Anti-Pattern
Applying `transition: all` causes performance lag (jank) and unexpected transitions during page resize or reflow. Animating layout properties (`width`, `height`, `top`, `left`) triggers browser layout recalculation on every frame.

### Code Diff
```css
/* ❌ VIOLATION (sloplint FAIL) */
.button {
  transition: all 0.3s ease;
}
.button:hover {
  height: 48px;
  transform: scale(1.08);
}

/* ✅ HALLMARK COMPLIANT (Specific properties & compositor-only transforms) */
.button {
  transition: 
    background-color var(--duration-fast) var(--ease-out),
    border-color var(--duration-fast) var(--ease-out),
    opacity var(--duration-fast) var(--ease-out);
}
```

---

## 6. Sizing Heros in `vh` (Failing Single-Viewport Benchmark)

### Anti-Pattern
Using `min-height: 100vh` causes mobile mobile address bar jumps. Spreading hero sections over 1500px requires the user to scroll before understanding the product.

### Directives
- Use `100dvh` or `100svh` instead of raw `100vh`.
- Keep the hero under 800px on desktop (`max-height: 800px`).
- Keep total copy in the hero under 70 words.
- Structure: One Offer → One Audience → One Primary Action.

---

## 7. Hardcoded Non-Token Values & Pure White/Black

### Anti-Pattern
Sprinkling `#ffffff`, `#000000`, `#6366f1`, or arbitrary pixel margins like `margin-top: 23px` directly in CSS rules.

### Directives
- Every color, spacing, radius, and duration MUST resolve through `:root` CSS variables.
- Pure `#ffffff` and pure `#000000` reflect harsh digital edges. Tint the paper/ink towards the primary brand hue (e.g. `#f4f5f6` or `#090a0b`).
- Adhere strictly to the 4px/8px layout grid.

---

## 8. Missing Interactive States & Accessibility Baselines

### Anti-Pattern
Providing only default and hover styles, omitting active, focus-visible, disabled, and loading states, and ignoring `prefers-reduced-motion`.

### Requirements
1. **Default**: Calibrated baseline contrast (WCAG AA `4.5:1` minimum).
2. **Hover**: Subtle feedback (`background-color`, `border-color`).
3. **Active**: Distinct tactile response.
4. **Focus-Visible**: Dedicated outline ring (`outline: 2px solid var(--border-focus); outline-offset: 2px;`).
5. **Disabled**: `aria-disabled="true"` with `cursor: not-allowed` and appropriate contrast.
6. **Loading**: Progress spinner or shimmer skeleton.
7. **Reduced Motion**: Mandatory `@media (prefers-reduced-motion: reduce)` block.
