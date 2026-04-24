# Ingest Rules

## Purpose

Ingest turns raw material into traceable source notes before any stable Wiki page is updated.

## Procedure

1. Read `../SCHEMA.md`, `../index.md`, and recent `../log.md`.
2. Classify the source into `raw/requirements`, `raw/designs`, `raw/reviews`, `raw/code-notes`, `raw/meetings`, `raw/cooper`, `raw/db`, or `raw/snapshots`.
3. Create a raw note using `page-templates/raw-note.md`.
4. Add or update the source id in `../sources/source-catalog.md`.
5. Only then compile durable facts into stable Wiki pages.

## Raw Immutability

- Do not rewrite captured raw content casually.
- If a source is superseded, create a new raw note and mark the old source as superseded in `sources/source-catalog.md`.
- For code facts, prefer small code-note raw files that name exact file paths and observed behavior.

## When To Skip Raw Capture

Skip only when the source is already a durable repo file and the stable page cites it directly through `sources/source-catalog.md`. Even then, add a source catalog entry.

