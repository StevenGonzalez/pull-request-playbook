# Example: Excellent Bug Fix PR

This example demonstrates how to document a bug fix so reviewers understand the root cause.

**Title**: `[Bug] Fix race condition in "Add to Cart" button`

---

## The Bug
Users reported that clicking "Add to Cart" rapidly multiple times resulted in negative inventory counts.
- **Issue**: #405
- **Severity**: High (Data integrity)

## The Fix
The `addToCart` function was reading the inventory level *before* previous async requests completed.
I implemented an optimistic UI update with a server-side validation check, and crucially, **disabled the button** while the request is pending.

## Reproduction Steps
1. Navigate to any Product Page with Low Stock (e.g., 2 items left).
2. Throttling network to "Slow 3G" in DevTools.
3. Click "Add to Cart" 5 times rapidly.
4. **Expected**: Should only add 2 items and disable button.
5. **Actual (Before)**: Added 5 items, resulting in inventory: -3.

## Tests Added
- `CartService.test.ts`: Added a test case that mocks concurrent requests ensuring inventory never drops below zero.
- `ProductPage.test.tsx`: UI test ensuring button receives `disabled={true}` prop on click.

## Verification
![Button Disabled State](https://placehold.co/400x100?text=Button+Disabled+Pending...)

---

### *Why this is excellent*
1. **Diagnosis**: It explains the *root cause* (async race condition), not just the symptom.
2. **Reproduction**: Gives the reviewer a clear path to verify the bug existed.
3. **Safety**: Explicitly mentions testing for data integrity.
