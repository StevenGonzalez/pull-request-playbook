# Creating Custom PR Templates

GitHub allows you to have multiple PR templates. This is great for teams that have different workflows for different types of changes.

## How to use these templates

1. **Option 1: Manual Copy-Paste**
   - Keep these markdown files in your repo.
   - Developers open the relevant file, copy the raw markdown, and paste it into their PR description.

2. **Option 2: GitHub Native Support (Recommended)**
   - Move these files to `.github/PULL_REQUEST_TEMPLATE/` folder in your repository.
   - Example: `.github/PULL_REQUEST_TEMPLATE/bug_fix.md`
   - When creating a PR, GitHub will allow you to append `?template=bug_fix.md` to the URL to pre-fill the description.
   - Or, users can select the template from the GitHub UI if you configure them properly.

## Configuring Multiple Templates

Create a `.github/PULL_REQUEST_TEMPLATE/` directory.
Add your markdown files there.

- `feature_request.md`
- `bug_fix.md`

When a user creates a PR, they can choose which template to use via query parameters:
`https://github.com/org/repo/compare/main...my-branch?template=feature_request.md`

## Default Template

You can also have a single default template at `.github/pull_request_template.md`. This will be used if no specific template is selected.
