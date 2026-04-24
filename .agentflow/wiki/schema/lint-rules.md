# Lint Rules

## Checks

- Every stable page has valid frontmatter.
- Every stable page appears in `../index.md`.
- Every `sources:` id exists in `../sources/source-catalog.md`.
- Relative links resolve.
- Raw notes are not overwritten without a log entry.
- Contradictions and open questions are linked from affected pages.
- Pages over roughly 200 lines are reviewed for splitting.
- Tags come from `../SCHEMA.md`.

## Severity

- P0: broken source reference, missing index entry for active page, unresolved contradiction affecting current work.
- P1: broken relative link, missing frontmatter, stale page with active status.
- P2: weak related links, missing tags, page too long.
- P3: style or naming drift.

## Output Format

Lint reports should include:

- Finding
- Severity
- File
- Evidence
- Suggested fix

