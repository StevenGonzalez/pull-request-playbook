# 👁️ The Reviewer's Guide

Code review is not about finding bugs (that's what tests are for). It's about maintaining code quality, sharing knowledge, and ensuring maintainability.

---

## The Golden Rule 🌟
**Review the code, not the person.**
Be kind, specific, and constructive.

---

## How to Review Efficiently

### 1. Understand the Goal First
Don't look at the code yet. Read the Title and Description.
- *Do I understand what problem this solves?*
- If the description is empty, ask the author to fill it out first.

### 2. Run the Code (If needed)
For UI changes or complex logic, pull the branch locally.
- Does it actually work?
- Does it look like the screenshots?

### 3. Start High Level
Look at the file structure.
- Are files in the right places?
- ample naming conventions?
- Is this architecturally sound?

### 4. Then Dive Deep
Look at the logic.
- Are there edge cases missing?
- Is there security exposure?
- Is the code readable?

---

## 🚦 Approval Tiers

| State | Meaning |
|-------|---------|
| **Request Changes** | There are blocking issues (bugs, design flaws) that MUST be fixed before merge. |
| **Comment** | Questions or non-blocking suggestions. "Nitpicks" go here. |
| **Approve** | The code is good enough to merge. It doesn't have to be perfect. |

### The "Good Enough" Principle
Do not hold a PR hostage for perfection. If the code is better than it was before, or fixes the problem without introducing new ones, approve it.

---

## 🚫 What NOT to Review (Let Automation do it)
Don't waste time commenting on:
- Semicolons
- Indentation
- Spacing
- Import order

**Action**: Set up Prettier/ESLint/Black/Gofmt to handle this automatically on commit.

---

[⬅️ Back to README](../README.md)
