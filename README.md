# Pull Request Playbook

> **The definitive guide to writing pull requests that get merged faster and reviewed better.**

A practical, opinionated playbook for developers who want to level up their pull request game. Whether you're a junior developer writing your first PR or a senior engineer mentoring a team, this guide provides battle-tested patterns, templates, and examples to make code reviews faster, healthier, and more effective.

---

## Table of Contents

- [Philosophy](#philosophy)
- [Quick Start](#quick-start)
- [The Anatomy of a Great PR](#the-anatomy-of-a-great-pr)
- [Templates](#templates)
- [Examples](#examples)
- [Anti-Patterns](#anti-patterns)
- [For Reviewers](#for-reviewers)
- [Advanced Topics](#advanced-topics)

---

## Philosophy

Great pull requests are not just about code - they're about **communication**, **respect for reviewers' time**, and **enabling better software**. The best PRs share these characteristics:

### 1. **Clear Intent**
Every PR should answer: *Why does this change exist?* Great PRs tell a story that connects business value to technical implementation.

### 2. **Right-Sized**
The ideal PR can be reviewed in 20-30 minutes. If it takes longer, it's probably too big. Small PRs get better reviews, ship faster, and have fewer bugs.

### 3. **Self-Documenting**
A reviewer shouldn't need to ask "what" or "why." The PR title, description, code comments, and commit messages should create a complete narrative.

### 4. **Respect for Time**
Code review is one of the most valuable activities in software development. Great PRs make the reviewer's job easier through clarity, context, and completeness.

### 5. **Review-Ready**
Before requesting review: tests pass, linting is clean, conflicts are resolved, and you've self-reviewed your own changes.

---

## Quick Start

**New to pull requests?** Start here:

1. **Read**: [The Anatomy of a Great PR](docs/anatomy.md) - understand the building blocks
2. **Use**: Pick a [template](templates/) that matches your PR type
3. **Study**: Review [real-world examples](examples/) with annotations
4. **Avoid**: Learn from common [anti-patterns](docs/anti-patterns.md)
5. **Practice**: Write your PR, then use the [checklist](docs/checklist.md) before submitting

**Reviewing PRs?** Jump to the [Reviewer's Guide](docs/reviewers-guide.md).

---

## The Anatomy of a Great PR

A great pull request has six essential components:

### 1. **The Title**
- Clear, specific, and scannable
- Follows a consistent format (e.g., `[Type] Brief description`)
- Examples:
  - ✅ `[Feature] Add user authentication with OAuth2`
  - ✅ `[Bug] Fix memory leak in WebSocket connection handler`
  - ❌ `Update stuff` (too vague)
  - ❌ `Fix issue #1234` (not self-documenting)

### 2. **The Description**
The most critical part. Should include:
- **What**: What changed?
- **Why**: Why was this change necessary?
- **How**: How was it implemented? (for complex changes)
- **Testing**: How was it tested?
- **Screenshots/Videos**: For UI changes
- **Breaking Changes**: Any backwards incompatibilities?
- **Related Issues**: Links to tickets, discussions, or docs

### 3. **The Commits**
- Atomic and logical (each commit = one logical change)
- Clear commit messages following [Conventional Commits](https://www.conventionalcommits.org/)
- Easy to bisect if things go wrong

### 4. **The Diff**
- Focused on one concern
- No unrelated formatting changes
- No commented-out code or debug logs
- Readable and scannable

### 5. **The Tests**
- New features include tests
- Bug fixes include regression tests
- All tests passing in CI
- Coverage metrics maintained or improved

### 6. **The Context**
- Links to related PRs, issues, or documentation
- Screenshots or recordings for visual changes
- Performance benchmarks for optimization work
- Migration guide for breaking changes

📚 **Deep Dive**: Read the complete [Anatomy Guide](docs/anatomy.md) for detailed explanations and examples.

---

## Templates

Copy-paste templates for common PR types:

| Template | Use Case | Link |
|----------|----------|------|
| **Feature** | New functionality | [View Template](templates/feature.md) |
| **Bug Fix** | Fixing defects | [View Template](templates/bugfix.md) |
| **Refactor** | Code improvements | [View Template](templates/refactor.md) |
| **Documentation** | Docs updates | [View Template](templates/documentation.md) |
| **Performance** | Speed/efficiency improvements | [View Template](templates/performance.md) |
| **Security** | Security patches | [View Template](templates/security.md) |

**Need a custom template?** See our [template guide](docs/creating-templates.md).

---

## Examples

Learn from real-world examples with detailed annotations:

- [**Excellent Feature PR**](examples/excellent-feature.md) - A full-featured implementation with great documentation
- [**Perfect Bug Fix**](examples/excellent-bugfix.md) - Clear problem statement and solution
- [**Smart Refactor**](examples/excellent-refactor.md) - Improving code without changing behavior
- [**Before & After**](examples/before-after.md) - Transforming bad PRs into great ones

---

## Anti-Patterns

Common mistakes and how to fix them:

### The "God PR" 
❌ **Problem**: 3,000 lines changed across 47 files  
✅ **Solution**: Break into smaller, focused PRs

### The "Mystery PR"
❌ **Problem**: No description, title is "fix stuff"  
✅ **Solution**: Write clear title and comprehensive description

### The "Kitchen Sink"
❌ **Problem**: Includes refactoring, new feature, and bug fixes  
✅ **Solution**: One concern per PR

### The "WIP Forever"
❌ **Problem**: Marked as draft for weeks with no updates  
✅ **Solution**: Either finish it or close it

📚 **Full List**: See [complete anti-patterns guide](docs/anti-patterns.md) with examples and fixes.

---

## For Reviewers

Great reviews are just as important as great PRs:

- [**Reviewer's Guide**](docs/reviewers-guide.md) - How to give effective, constructive feedback
- [**Review Checklist**](docs/review-checklist.md) - What to look for when reviewing
- [**Comment Templates**](docs/review-comments.md) - Effective ways to phrase feedback
- [**Handling Conflicts**](docs/review-conflicts.md) - Resolving disagreements gracefully

**Key Principle**: Review the code, not the person. Be kind, be specific, be helpful.

---

## Advanced Topics

Level up your PR game:

- [**PR Sizing Strategies**](docs/sizing.md) - Techniques for breaking down large work
- [**Stacking PRs**](docs/stacking.md) - Managing dependent pull requests
- [**Draft PRs**](docs/drafts.md) - When and how to use work-in-progress PRs
- [**Monorepo PRs**](docs/monorepo.md) - Special considerations for monorepos
- [**Migration PRs**](docs/migrations.md) - Handling large-scale changes
- [**Performance PRs**](docs/performance.md) - Documenting benchmarks and optimizations
- [**Security PRs**](docs/security.md) - Handling sensitive changes responsibly

---

## License

MIT (c) 2026 Steven Gonzalez

---

## Why This Matters

Every year, developers spend **millions of hours** in code review. A great pull request:
- ✅ Gets reviewed faster (often same-day)
- ✅ Receives better, more thoughtful feedback
- ✅ Ships with fewer bugs
- ✅ Creates better documentation
- ✅ Builds trust with your team
- ✅ Accelerates your career

**Writing great PRs is a skill** - and like any skill, it can be learned, practiced, and mastered.

---

<div align="center">

**⭐ Star this repo** if you found it helpful!

Made with ❤️ for the developer community

</div>
