# Migrations & Large Refactors

Renaming a core component? Moving to a new folder structure? Upgrading a framework?
These changes are noisy and scary.

## Strategy: The "Reviewable" Migration

### 1. Separate "Move" from "Change"
NEVER change logic while moving files. Git cannot track the history easily if you modify the file content and rename it simultaneously.
- **PR 1**: `git mv old.ts new.ts` (100% moves, 0% logic changes)
- **PR 2**: Update imports / Clean up code.

### 2. The "Deprecation" Pattern
Don't delete the old thing immediately.
1. Create `NewService`.
2. Mark `OldService` as `@deprecated`.
3. Route `OldService` to call `NewService` internally (if possible).
4. Migrate consumers slowly over several PRs.
5. Delete `OldService`.

### 3. Script It
If you are doing a repetitive change (e.g. renaming a prop in 500 files), write a "codemod" script.
- Commit the script in the PR.
- Reviewers can view the script to trust the changes, rather than reading 500 files manually.
