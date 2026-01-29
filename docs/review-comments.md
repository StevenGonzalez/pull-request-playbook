# Comment Templates

Phrasing matters. Here are templates for common review situations that differ in tone.

## Asking for clarification
> "Hi! I'm not sure I understand the logic here. Could you explain why we need this extra check?"

## Suggesting a non-blocking improvement (Nitpick)
> "Nit: We could simplify this by using `map()` here, but it's fine as-is."

## Pointing out a bug
> "Major: This line will throw an error if `user` is null. We should add a null check."

## Praising good code
> "Nice! I like how you extracted this logic into a separate hook. Much cleaner."

## requesting architectural changes
> "I see what you're doing, but I'm concerned about the performance impact of this approach. have we considered X instead? Happy to hop on a call to discuss."

## The "Blocking" vs "Non-Blocking" Prefix
Adopt a convention to make expectations clear:
- `[BLOCKER]` - Must fix.
- `[NIT]` - Fix if you want, but not required.
- `[QUESTION]` - I just need info.
- `[PRAISE]` - Good job.
