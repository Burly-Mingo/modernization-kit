# Codex Compatibility Layer

This repository now supports **Kiro + Codex side-by-side** without a fork.

- Kiro reads `.kiro/`
- Codex reads `.codex/`
- Both share the same core methodology and generated deliverables

## Quick start in Codex

1. Open this repository at the workspace root.
2. Start your session by loading `.codex/context/system-instructions.md` as persistent context.
3. Follow `.codex/runbooks/phase-workflow.md` phase-by-phase.
4. Apply `.codex/checklists/quality-gates.md` before moving to the next phase.

## Deliverables

Use the same output documents defined by the modernization kit (e.g., `DISCOVERY_SUMMARY.md`, `ASSESSMENT.md`, `MODERNIZATION_PLAN.md`).

## Design goal

This layer mirrors the intent of Kiro steering/specs/hooks while staying CLI-agent friendly for Codex.
