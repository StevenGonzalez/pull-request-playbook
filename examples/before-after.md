# Before & After: The Makeover

See the difference between a "Lazy PR" and a "Pro PR" for the exact same code change.

---

### The "Lazy" PR (Bad)

**Title**: `fix styles`

**Description**:
*(Empty)*

**Files Changed**:
- 12 files
- `login.css`, `header.tsx`, `utils.ts`...

**Why this fails**:
- "fix styles" could mean anything.
- No screenshots.
- Changes in `utils.ts` seem unrelated to styles?
- Reviewer has to reverse-engineer the author's intent.

---

### The "Pro" PR (Good)

**Title**: `[UI] Align Login Page with 2026 Design System`

**Description**:
## Summary
Updates the Login Page input fields and buttons to match the new Figma Design System tokens.

## Changes
- **CSS**: Replaced hardcoded hex values with CSS variables (`--color-primary`).
- **Cleanup**: Removed unused `formatDate()` helper from `utils.ts` while I was here (separate commit).

## Visuals
| Old | New |
|-----|-----|
| ![Old](...) | ![New](...) |

## Testing
- Verified on Mobile and Desktop viewports.

---

### The Takeaway
The code might be identical, but the **Good PR** gets reviewed and merged in 10 minutes with praise. The **Bad PR** sits for 3 days and gets confused questions.
