# Example: Excellent Refactor PR

Refactoring is risky. This example shows how to mitigate that risk through documentation.

**Title**: `[Refactor] Modularize Monolithic "UserService"`

---

## Purpose
`UserService.ts` had grown to 4,000 lines. It handled Authentication, User Profile, *and* Billing. This made the file hard to read and caused frequent merge conflicts.

This PR extracts the Billing logic into its own domain service.

## Changes
1. Created `src/services/billing/` directory.
2. Moved `processPayment`, `getInvoices`, and `updateCreditCard` methods from `UserService` to `BillingService`.
3. Updated all 45 references in the codebase to use the new `BillingService`.
4. **No logic changes were made** inside the methods, only inputs/outputs were updated to match the new class structure.

## Risk Assessment
- **Low**: Since code was moved verbatim, logic errors are unlikely.
- **Medium**: Import paths changed across many files.

## Verification
- Ran existing test suite: `npm test` -> **All passed**.
- Manually verified the "Update Credit Card" flow in the staging environment.

---

### *Why this is excellent*
1. **Scope**: It limits itself to *moving* code, not rewriting it.
2. **Honesty**: It admits the risk (imports changing) and how it was mitigated.
3. **Clarity**: It explicitly lists what moved and where.
