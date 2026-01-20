# 📉 PR Sizing Strategies

Size matters. Small PRs are reviewed faster, merge with fewer conflicts, and have fewer bugs.

## The Optimal Size
Research suggests the sweet spot for a PR is **under 400 lines of code**.
Review effectiveness drops significantly after 400 lines. At 1,000 lines, reviewers often just "scan" rather than review.

## Strategies to Shrink PRs

### 1. Vertical Slicing 🍰
Instead of building the whole "User Profile" feature at once (Database + API + Frontend + CSS), build thin slices:
- PR 1: Database Model & Migration
- PR 2: API Endpoint & Tests
- PR 3: Frontend Component
- PR 4: Integration styles

### 2. Isolate Refactoring 🧹
If you need to rename a class before adding a feature:
- PR 1: Rename the class (Automated refactor, safe to merge)
- PR 2: Add the feature using the new name

### 3. Feature Flags 🚩
Merge code that isn't fully ready by hiding it behind a flag.
- PR 1: Build the backend logic (hidden)
- PR 2: Build the UI (hidden)
- PR 3: Enable the flag

## When is a Large PR Okay?
- **generated code**: `package-lock.json` or generated clients.
- **Find/Replace**: Renaming a method across 50 files.
- **Deletions**: Removing 5,000 lines of dead code is always welcome!
