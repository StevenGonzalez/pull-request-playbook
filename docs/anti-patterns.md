# Pull Request Anti-Patterns

Even well-intentioned developers fall into these traps. Recognizing these anti-patterns is the first step to avoiding them.

---

## 1. The "God PR"
**The Symptom**: A massive PR with 50+ changed files and 2,000+ lines of code.
**Why it's bad**: 
- Impossible to review thoroughly.
- High risk of hidden bugs.
- Blocks other work (merge conflicts).
- Reviewers will procrastinate reviewing it.

**Solution**:
- **Feature Flag it**: Merge the backend first, then the frontend.
- **Stacking**: Break it into 3 dependent PRs (Part 1, Part 2, Part 3).
- **Atomic Commits**: If you can't break the PR, at least ensure every commit is clean and reviewable one-by-one.

---

## 2. The "Mystery PR"
**The Symptom**: 
- Title: `Update logic`
- Description: *Empty* or just `Fixes bug`.
**Why it's bad**: 
- Reviewer has no context.
- Wastes time asking "What does this do?".
- Future maintainers won't know why this change happened.

**Solution**:
- Use the [PR Templates](../templates/).
- Always answer: **What** changed, **Why** it changed, and **How** to test it.

---

## 3. The "Kitchen Sink"
**The Symptom**: A PR that claims to be a "Login Feature" but also:
- Fixes a typo in the footer.
- Upgrades dependencies.
- Reformats the helper library.
**Why it's bad**: 
- If the Login Feature has a bug, you have to revert the *fixes* and *upgrades* too.
- Makes the diff noisy and hard to read.

**Solution**:
- **One Concern Per PR**.
- If you see a typo, fix it in a separate valid branch/PR, or at least a separate commit that is clearly labeled.

---

## 4. The "Formatting Bomb"
**The Symptom**: You changed one line of logic, but your IDE re-indented the whole file. The diff shows 400 changes.
**Why it's bad**: 
- Hides the needle in the haystack.
- Reviewers can't see the actual logic change.

**Solution**:
- Configure your IDE to respect project settings (EditorConfig).
- Run the project's linter/formatter *before* starting work.
- If you want to reformat a legacy file, do it in a dedicated "Refactor/Format" PR first.

---

## 5. The "WIP Forever"
**The Symptom**: A draft PR opened 3 weeks ago. The author pushes to it occasionally.
**Why it's bad**: 
- Code goes stale (drift from main).
- Clutters the PR list.
- Unclear if it's ready for help or just a backup.

**Solution**:
- Use Draft PRs for *active* work only.
- If you pause work, close the PR and tag it `wontfix` or `paused`.

---

## 6. The "Sleeper Agent"
**The Symptom**: Committing commented-out code.
```javascript
// const oldFunction = () => { ... }
const newFunction = () => { ... }
```
**Why it's bad**: 
- "Zombie code" rots. It won't compile in a month.
- Git has history; you don't need to keep the old code in the file.

**Solution**:
- Delete it. Git will remember it efficiently.

---

[Back to README](../README.md)
