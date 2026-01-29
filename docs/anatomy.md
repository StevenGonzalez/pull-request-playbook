# The Anatomy of a Great Pull Request

A great pull request isn't just code; it's a complete package that communicates *context*, *intent*, and *quality*. This guide breaks down the essential components of a perfect PR.

---

## 1. The Title

Your title is the first thing a reviewer sees. It should be specific, searchable, and follow a consistent pattern.

### The Formula
`[Type] (Scope) Description`

- **Type**: What kind of change is this? (`Feature`, `Bug`, `Refactor`, `Docs`, `Chore`)
- **Scope**: (Optional) Which part of the app does this touch? (`Auth`, `API`, `Frontend`)
- **Description**: A concise summary in the imperative mood ("Add" not "Added").

### Examples

| Status | Title | Why |
|:---:|---|---|
| ✅ | `[Feature] Add Google OAuth2 login provider` | Clear type, specific feature |
| ✅ | `[Bug] (API) Fix null pointer in user serialization` | Scoped, describes the fix |
| ✅ | `[Refactor] Move utility functions to shared lib` | Describes the action taken |
| ❌ | `Update login` | Too vague. Update what? |
| ❌ | `Fix bug` | Which bug? |
| ❌ | `WIP` | Tells me nothing about the content |

---

## 2. The Description

The description is your chance to advocate for your code. It should tell a story.

### Essential Sections

#### **Summary**
A high-level overview of the changes.
> *Implemented the new OAuth flow using the Google Identity Services SDK. This replaces the deprecated Google Sign-In library.*

#### **Motivation**
Why are we making this change? Connect it to business value or technical debt.
> *The old library is being sunset in June. This migration ensures users can still sign in and improves security compliance.*

#### **Implementation Details**
Highlight complex logic or architectural decisions.
> *Created a `GoogleAuthProvider` class that implements our `IAuthProvider` interface. Standardized error handling to map Google errors to our internal `AuthError` types.*

#### **Test Plan**
How can the reviewer verify this?
> - *Unit tests added for the provider adapter*
> - *Manual test: Logged in with a test account on staging*
> - *Tested failure case: Network disconnect during handshake*

### Pro Tip: Use Visuals 📸
If your PR changes the UI, **screenshots or screen recordings are mandatory**.
- **Before/After** side-by-side images are incredibly helpful.
- **GIFs/Videos** for interactions/animations.

---

## 3. The Commits

Commits tell the history of your changes.

### Atomic Commits
Each commit should do **one thing** and do it well.
- ✅ `Add user model`
- ✅ `Create API endpoint for user creation`
- ✅ `Update documentation`

Avoid "Kitchen Sink" commits:
- ❌ `More work`
- ❌ `Fix stuff` (which stuff?)
- ❌ `Commit 1`

### Interactive Rebase is Your Friend
Before submitting, clean up your history. Squash typos (`Fix typo`, `oops`) into the relevant commits.

---

## 4. The Tests

Code without tests is effectively broken. Your PR should include:

- **Unit Tests**: For logic, utilities, and individual components.
- **Integration Tests**: For API endpoints or module interactions.
- **Regression Tests**: If fixing a bug, add a test that reproduces the bug to ensure it never comes back.

**The "Green Build" Standard**:
Reviewers should never have to review a PR with failing tests. Ensure CI is green before requesting a review.

---

## 5. The Diff

Minimize cognitive load for your reviewer.

- **Self-Review First**: Read your own diff on GitHub/GitLab/Azure DevOps *before* assigning reviewers. You'll catch 80% of typos yourself.
- **No Noise**: Remove `console.log`, commented-out code, or inadvertent whitespace changes.
- **Formatting**: run your linter/formatter (Prettier, ESLint, etc.) automatically. Don't waste a human's time on comma placement.

---

## 6. Context Links

Connect the dots.
- `Closes #123` (Auto-closes the issue)
- `Depends on #456` (If this PR needs another one first)
- `Design Spec: [Figma Link]`
- `Documentation: [Confluence Link]`

---

## Checklist for Success

Before you click "Create Pull Request":
- [ ] Title follows the standard format
- [ ] Description answers "What" and "Why"
- [ ] Screenshots added for UI changes
- [ ] Tests passed locally
- [ ] Self-review completed
- [ ] Linter/Formatter run

---

[⬅️ Back to README](../README.md)
