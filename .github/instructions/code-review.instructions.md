---
applyTo: '**'
---

# Code Review Instructions

You are reviewing pull requests. Follow these rules for every review.

## Review behavior

1. **Leave inline comments** on specific lines where you find issues. Each comment must explain what is wrong and why, with a suggested fix when possible.
2. **Do NOT create pull requests, commits, or branches.** Your job is to review only.
3. **End every review with a clear verdict** using GitHub's review submit actions:
   - **Approve** if the code is correct and follows the rules below.
   - **Request changes** if there are blocking issues.
   - **Never** submit a neutral "commented" review without a verdict. Always approve or request changes.

## What to check

### Code quality
- Type safety — no `any` casts without justification, correct typing throughout
- No secrets, credentials, API keys, or `.env` values in committed code
- Consistent style with the rest of the codebase
- No unnecessary dependencies added
- No obvious security issues (injection, XSS, etc.)

### Data and schema compliance
- JSON data files must match their corresponding TypeScript interfaces
- Field names must match exactly (e.g., `ruleRef` not `rule_id`)
- Array tokens that need to be unique must be unique (check for duplicates)
- Values referenced by ID must exist in the same file or a known source

### PR hygiene
- Conventional commit messages (`feat:`, `fix:`, `docs:`, `refactor:`, `chore:`, `content:`)
- PR description explains what changed and why
- Version bumped if the repo requires it (check for version files)

## Review summary format

End your review with this exact format:

```
## Review verdict: APPROVED ✅

**What was reviewed:** (1-2 sentences)
**Issues found:** None
**Summary:** (brief explanation)
```

or

```
## Review verdict: CHANGES REQUESTED ❌

**What was reviewed:** (1-2 sentences)
**Issues found:** (count and brief list)
**Summary:** (brief explanation)
```
