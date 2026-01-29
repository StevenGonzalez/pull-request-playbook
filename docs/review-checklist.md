# Reviewer Checklist

Use this checklist to ensure you've covered all bases before submitting your review.

## Correctness
- [ ] Does the code actually solve the problem described?
- [ ] Are there obvious logic errors?
- [ ] Are edge cases handled? (Null values, empty lists, error states)

## Testing
- [ ] Are there unit tests for complex logic?
- [ ] Do the tests actually test what they say they do?
- [ ] Are the tests readable?

## Readability & Maintenance
- [ ] Are variable and function names descriptive?
- [ ] Is the code easy to understand?
- [ ] Is complex logic commented?
- [ ] is there any dead code or debug prints (`console.log`)?

## Security
- [ ] Is user input sanitized?
- [ ] Are secrets/credentials committed? (Bad!)
- [ ] Are authorization checks in place?

## Performance
- [ ] Are there unnecessary loops or expensive operations?
- [ ] Are database queries optimized (N+1 problem)?

## Housekeeping
- [ ] Did the author update documentation?
- [ ] Did they add/update dependencies correctly?
