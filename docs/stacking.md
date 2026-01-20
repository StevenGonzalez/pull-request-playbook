# 🥞 Stacking PRs

Stacked PRs (or Dependent PRs) allow you to break large changes into reviewable chunks without blocking your own progress.

## The Concept
Instead of one massive branch:
`main` -> `feature-giant`

You create a chain:
`main` -> `part-1-models` -> `part-2-api` -> `part-3-ui`

## Workflow

1. **Create Part 1**
   `git checkout -b part-1-models main`
   (Do work, commit, push)
   Create PR: `Part 1` (Target: `main`)

2. **Create Part 2**
   `git checkout -b part-2-api part-1-models`
   (Do work, commit, push)
   Create PR: `Part 2` (Target: `part-1-models` OR `main`)

   > **Note**: Targeting `part-1-models` shows only the *new* changes in the diff, which is easier to review. Targeting `main` shows everything combined.

3. **Handling Updates**
   If you change `Part 1`, you must rebase `Part 2` onto it.
   `git checkout part-2-api`
   `git rebase part-1-models`
   `git push -f`

## Tools
Managing stacks manually involves a lot of git gymnastics. Consider tools like:
- **Graphite.dev**
- **gh-stack** (CLI tool)
