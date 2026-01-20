# 🛡️ Security PRs

Handling security fixes requires discretion and thoroughness.

## Handling Vulnerabilities (CVEs)
If you are fixing a **public** vulnerability:
- Link the CVE.
- Upgrade the package.
- Verify that `npm audit` or your security scanner is green.

If you are fixing a **private/0-day** vulnerability (Internal):
- **DO NOT** post the exploit details in the PR description if the repo is widely accessible.
- Use a generic title: `Fix validation logic in user profile`.
- Link to the private issue tracker for details.

## Sensitive Data
- **Never commit secrets**, even to test.
- If you accidentally commit a secret, **rotate it immediately**. Reverting the commit is not enough (it's still in git history).

## The Security Review
Explicitly request a review from the security champion/team if you touch:
- Authentication / Authorization logic
- Cryptography / Hashing
- PII (Personally Identifiable Information) handling
- File uploads / XML parsing
