# Example: Excellent Feature PR

This is an example of what a high-quality Feature PR looks like.

**Title**: `[Feature] Add Dark Mode toggle to User Settings`

---

## Summary
Introduces a system-aware Dark Mode theme to the dashboard. Users can now toggle between Light, Dark, and System (Auto) preferences in the settings page.

## Motivation
User research showed 40% of our users access the dashboard in low-light environments. This feature improves accessibility and reduces eye strain. Relates to [User Story 302](http://jira.com/302).

## Implementation Details
- **ThemeContext**: Created a React Context to manage theme state (`src/context/ThemeContext.tsx`).
- **Tailwind Config**: Extended tailwind.config.js to support 'class' based dark mode.
- **LocalStorage**: detailed preference is persisted in `localStorage` key `theme_preference`.
- **System Listener**: Added a listener for `prefers-color-scheme` media query to auto-switch when "System" is selected.

## Screenshots

| Light Mode (Default) | Dark Mode | Settings UI |
|----------------------|-----------|-------------|
| ![Light](https://placehold.co/200x150?text=Light+Mode) | ![Dark](https://placehold.co/200x150?text=Dark+Mode) | ![Settings](https://placehold.co/200x150?text=Settings+Component) |

## Test Plan
**Manual Verification**:
1. Go to Settings > Appearance.
2. Select "Dark Mode" -> Verify UI turns dark immediately.
3. Refresh page -> Verify Dark Mode persists.
4. Select "System" -> Change OS theme -> Verify UI follows OS.

**Automated Tests**:
- `ThemeContext.test.tsx`: Unit tests for state logic and storage persistence.
- `Settings.test.tsx`: Component test ensuring buttons trigger state changes.

## Related Issues
- Closes #89
- Depends on #85 (Icon set update)

## Breaking Changes
None. The default remains "Light Mode" for existing users until they change it.

---

### *Why this is excellent*
1. **Visuals**: Screenshots make it immediately obvious what changed.
2. **Context**: Explains *why* (eye strain, user research) not just *what*.
3. **Robustness**: Handles edge cases like page refresh and system preferences.
