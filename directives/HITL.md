# HITL.md

## ⚠️ Human In The Loop

This file contains observations that require human validation.

It is a controlled buffer between:

- agent discovery
- human decision
- doctrine (`BARIO.md`)

---

## Rules

- entries are NOT authoritative
- entries MUST NOT influence agent decisions
- this file is **write-only for agents**
- only humans may promote entries into `BARIO.md`

Agents MUST:

- append new valid observations
- NEVER modify or delete existing entries
- keep entries minimal and factual

---

## Constraints

Only add an entry if:

- the pattern appears at least twice
- it may impact architecture, naming, or workflow

If unsure:

→ DO NOT add  
→ DO NOT assume

---

## Entry Template

- id: hitl-XXXX
- observation:
- location:
- evidence:
- rationale:

---

## Entries

- id: hitl-0001
- observation: Required validation tooling is missing for pre-commit checks.
- location: repository root
- evidence: `task lint` fails with `task: command not found`; `Taskfile.yml` and `mise.toml` are absent.
- rationale: `BARIO.md` requires formatting and linting before commits, with required tools declared in `mise.toml`.

- id: hitl-0002
- observation: Repository formatting rule is missing.
- location: repository root
- evidence: `Taskfile.yml` defines `lint` and `lint:design`, but no formatting task or formatter is defined.
- rationale: `BARIO.md` requires formatting through a repository-defined formatter before commits.

- id: hitl-0003
- observation: The canonical stylesheet was moved out of `HITL/` and edited, contradicting a frozen human brief.
- location: `brand/style.css`, `HITL/01-harmonize-credimi-extras.md`
- evidence: `HITL/01-harmonize-credimi-extras.md` names `HITL/style.css` as the canonical design input and requires byte-equality tests against it. On human instruction the file was moved to `brand/style.css` and merged with the design system's `colors_and_type.css`; its SHA-256 pin no longer applies. The four logo SVGs moved to `brand/logos/` unchanged, so their pins still verify.
- rationale: The frozen brief and the current asset layout disagree. Either the brief is superseded and should be reissued, or the merge should be reverted. Only a human can decide which.

- id: hitl-0004
- observation: Both empty-state illustrations named by the design spec are unusable.
- location: Credimi Design System project, `assets/404-computer.svg` and `assets/maintenance.svg`
- evidence: Each file is a `<rect>` filled by a pattern referencing an `<image>` element that carries no data. Nothing renders. `DESIGN.md` §9 and §12 require an illustration in every empty and error state.
- rationale: The requirement cannot be met until working files exist upstream.
