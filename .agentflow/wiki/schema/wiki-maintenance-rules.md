# Wiki Maintenance Rules

## Always Orient First

For any Wiki task:

1. Read `SCHEMA.md`.
2. Read `index.md`.
3. Read recent `log.md`.
4. Read the directly related stable pages.

## Query Mode

- Answer from stable Wiki pages first.
- Use raw/source files only to verify, fill gaps, or resolve conflicts.
- Cite stable pages and source ids in the answer.
- If the answer is reusable, propose adding it to `queries/`.

## Update Mode

- Preserve source traceability.
- Keep edits narrow.
- Update `index.md` and `log.md`.
- Add contradictions/open questions instead of flattening uncertainty.
- Do not modify unrelated raw files.

## Maintenance Cadence

- After significant project docs or code changes: consider ingest/update.
- Before major design or implementation work: run query orientation.
- Before relying on Wiki for decisions: run a quick lint on relevant pages.

