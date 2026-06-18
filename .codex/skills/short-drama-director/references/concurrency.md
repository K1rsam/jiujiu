# Concurrency

Use this reference only for subagent or concurrent production.

## Real Concurrency

A stage can be called concurrent only if it has:

- Task package IDs and assigned episode or scene ranges.
- Independent temporary result paths.
- Subagent returned evidence packages.
- Master merge and review records.

Without those, call the work staged generation or master review, not concurrency.

## Task Package

Use `TASK_SCHEMA_V4` or newer. Each package must include:

- Task range.
- Maturity and complexity labels.
- Project fixed rules and output directory.
- Source-script excerpt or read-only snapshot.
- Scene snapshot and director layer.
- Asset index.
- Required evidence cards.
- Unit lock requirement.
- Dialogue-capacity gate requirement.
- Platform-safety requirement when relevant.
- Output boundary: final units plus evidence package for master review; no shared file writes.

## Subagent Rules

- Do not read or edit original `.docx`.
- Do not edit shared project rules, asset library, source script, or final directory.
- Do not add major settings, plot-changing props, clues, events, relationships, or action outcomes.
- If evidence cards, unit locks, source coverage, dialogue-capacity planning, action vocabulary, sound field, transitions, or safety replacement cannot be completed, stop and return the reason instead of writing final prose.

## Required Return

Subagent results must include:

- Generated shot units.
- Used asset IDs.
- Source-fidelity self-check.
- Evidence-card completion status.
- Unit-lock pass table.
- Source coverage summary.
- Platform-safety replacement summary when relevant.
- Dedicated action vocabulary summary.
- Scene sound-field summary.
- Transition summary.
- Dialogue-capacity summary: long or continuous dialogue body character count, planned duration, target chars/sec, and whether extra units were needed.
- High-frequency generic action risk.
- Return-before-merge self-test: fields, duration, sound, safety, repetition, coverage.
- Dialogue-density self-test: every spoken line, VO, and OS must include duration fit; lines above 4.5 Chinese chars/sec need notes, and above 5.0 must be reworked before returning.

The master strips evidence and process content from final shot scripts.

## Master Merge

The master must:

- Validate the evidence package before reading prose as final.
- Reject missing evidence instead of filling it in after the fact.
- Check order, field format, duration, source fidelity, safety, repetition, sound, transitions, and score.
- Run dialogue-capacity and dialogue-density scans before approving final prose, including phone VO and long OS. If capacity should have required extra units, return to unit design rather than squeezing timings.
- Keep final scripts clean of task-package and evidence content.
- Score each episode by `quality-gates.md`.
