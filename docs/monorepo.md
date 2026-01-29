# Monorepo PRs

In a Monorepo (multiple projects in one repo), PRs have unique challenges.

## 1. Scope Containment
If you touch `packages/ui-library` and `apps/web-dashboard`, consider splitting them if they are loosely coupled.
- **PR 1**: Release new version of `ui-library`
- **PR 2**: Bump version in `web-dashboard`

## 2. CI Impact
Monorepo CI can be slow.
- Should a change in `documentation` trigger the `backend` test suite?
- Ensure your CI pipeline uses **change detection** (like Nx, TurboRepo, or Bazel) to only run affects tests.

## 3. The "Codeowner" Problem
Monorepos often have many code owners. A PR touching 5 apps might automatically tag 15 people.
- **Be proactive**: Remove reviewers who aren't actually needed.
- **Ping specific people**: "I specifically need input from @team-auth on the session logic."
