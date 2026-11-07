# Verification Scripts & Linter Suite

This directory contains standalone, zero-dependency Node.js scripts that verify and enforce the Hallmark, Taste, and Impeccable design and consistency standards.

Both tools require **Node >= 18** and run cleanly in CI/CD pipelines, pre-commit hooks, or interactive agent loops.

---

## 1. `sloplint.mjs` — Hallmark Anti-Slop Linter

`sloplint.mjs` inspects HTML, CSS, JSX, TSX, Vue, Svelte, and Astro source files against the strict Hallmark design floor.

### Usage
```bash
# Lint specific files
node scripts/sloplint.mjs src/index.html src/styles.css

# Lint all frontend files in a project
node scripts/sloplint.mjs $(find src -name "*.html" -o -name "*.css" -o -name "*.tsx")

# Pre-audit mode (shows warnings without failing build)
node scripts/sloplint.mjs --before src/index.html
```

### CLI Flags
| Flag | Description |
| :--- | :--- |
| `<files...>` | One or more file paths to inspect. |
| `--before` | Runs in diagnostic mode: does not exit with code 1 on failures (useful for pre-redesign baseline audits). |
| `--genre=<name>` | Selects design genre expectations (e.g., `modern-minimal`, `editorial`, `developer`). |
| `--tokens-only` | Validates only token definitions and `:root` variables, skipping component-level rules. |

### Diagnostic Severities & Exit Codes
- **`FAIL`**: Strict anti-slop violations (e.g. missing Hallmark stamp, `transition: all`, untokenized gradients, raw `vh` hero sizing, missing reduced motion).
- **`REFLEX`**: AI habitual reflex patterns (e.g. pure `#ffffff` or `#000000`, non-4px scale margins, emojis in UI).
- **`WARN`**: Polishing recommendations (e.g. low contrast ratios, unthemed scrollbars, excessive hero paragraph length).

**Exit Code Behavior:**
- **`0`**: Clean or warnings only (in `--before` mode, exits 0 regardless).
- **`1`**: One or more `FAIL` or `REFLEX` violations detected. Blocks CI and deployment.

---

## 2. `consistency.mjs` — Cross-File Design Consistency Checker

`consistency.mjs` performs AST and pattern-based audits to verify that design tokens and styling conventions remain uniform across multiple files in a repository.

### Usage
```bash
node scripts/consistency.mjs --dir=src
```

### CLI Flags
| Flag | Description |
| :--- | :--- |
| `--dir=<path>` | Root directory of the frontend project to scan. |
| `--tokens=<path>` | Path to central token file (e.g., `src/tokens.css`). |
| `--strict` | Enforces exact token usage for every spacing, radius, and color rule. |

### Exit Codes
- **`0`**: No drift detected. Design tokens and styles are fully consistent.
- **`1`**: Token drift, orphan styles, or undeclared font families detected.

---

## 3. Extending the Linter with Custom Rules

To add a new rule to `sloplint.mjs`:
1. Open `scripts/sloplint.mjs`.
2. Locate the checks section (e.g., `function checkXX(ctx)`).
3. Use the helper `report(ruleId, severity, filePath, line, message, fix)`:
   ```javascript
   function checkMyCustomRule(ctx) {
     for (const doc of ctx.docs) {
       for (const rule of doc.rules) {
         if (rule.property === 'outline' && rule.value === 'none') {
           report(99, 'FAIL', doc.file, rule.line, 
             'outline: none removes keyboard focus indicator', 
             'Use :focus-visible with a visible outline ring instead');
         }
       }
     }
   }
   ```
4. Register the new check function in `runChecks(ctx)`.
