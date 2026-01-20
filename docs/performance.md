# ⚡ Performance PRs

Optimizing code requires proof, not just intuition.

## The Benchmark Rule
**"No Optimization without Measurement"**

If you submit a PR claiming "Improves list rendering performance," you must provide numbers.

### How to document
1. **Scenario**: "Scrolling the user list with 10k items."
2. **Environment**: "Chrome v110 on MacBook Pro M1."
3. **Metric**: "Average FPS / Scripting time."

### Example Table
| Metric | Main Branch | User List Branch | Diff |
|--------|-------------|------------------|------|
| Scripting Time | 450ms | 120ms | -73% |
| Memory Usage | 45MB | 44MB | ~0% |

## Profiling Evidence
Attach screenshots of the **DevTools Performance Tab** (Flame chart) showing the reduction in work.
