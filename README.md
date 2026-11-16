# Nuanu-com/.github

Shared GitHub Actions workflows for the Nuanu-com organization.

## Claude reviewer
`.github/workflows/claude.yml` is a reusable workflow that:
- automatically reviews every non-draft PR (inline comments + summary), and
- automatically requests a review from `rizgust` on every PR (input `human_reviewers`),
- responds to `@claude` mentions in issues, PR comments, and reviews.

Each repo opts in with a small caller at `.github/workflows/claude.yml` that uses
`Nuanu-com/.github/.github/workflows/claude.yml@main` passing only `ANTHROPIC_API_KEY` (not `secrets: inherit`, so other org secrets are never exposed to Claude).

Requires the org secret `ANTHROPIC_API_KEY` and the Claude GitHub App
(https://github.com/apps/claude) installed on the org.
