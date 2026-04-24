# Compile Rules

## Purpose

Compile turns raw/source-backed facts into stable, navigable Wiki pages.

## Procedure

1. Search `../index.md` for an existing page.
2. Read related pages before editing.
3. Preserve prior claims unless a newer source clearly supersedes them.
4. Add citations through `sources:` frontmatter and inline path references where useful.
5. Update `../index.md` and append `../log.md`.

## Page Creation Threshold

Create a stable page when one of these is true:

- The topic is central to App Center / AgentFlow operation.
- The topic appears in multiple raw sources.
- The answer will likely be asked again.
- The page helps navigate code, design, or review artifacts.

## Conflict Handling

If sources disagree, do not silently choose one. Create or update a contradiction page using `page-templates/contradiction.md`, then link it from affected pages.

