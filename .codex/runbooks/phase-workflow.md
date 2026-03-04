# Codex Phase Workflow

This workflow maps the Kiro-native process to Codex execution.

## Phase map

### Phase 0 — Discovery
- Source material: `.kiro/specs/phase-0-discovery/*`
- Output: `DISCOVERY_SUMMARY.md`
- Goal: gather business context, regulatory constraints, infrastructure facts, and modernization objectives.

### Phase 1 — Codebase Analysis
- Source material: `.kiro/specs/phase-1-codebase-analysis/*`
- Output: `ASSESSMENT.md` per app + `CONSOLIDATED_ASSESSMENT.md`
- Goal: produce factual architecture assessment and cross-application coupling analysis.

### Phase 2 — Pain Points
- Source material: `.kiro/specs/phase-2-pain-points/*`
- Output: `PAIN_POINTS.md`
- Goal: prioritize user pain, operational friction, and business impact.

### Phase 3 — Target Architecture
- Source material: `.kiro/specs/phase-3-target-architecture/*`
- Output: `TARGET_ARCHITECTURE.md`
- Goal: define future-state architecture, migration patterns, and buy-vs-build decisions.

### Phase 4 — Modernization Plan
- Source material: `.kiro/specs/phase-4-modernization-plan/*`
- Output: `MODERNIZATION_PLAN.md`
- Goal: sequence execution, estimate effort/cost, and define risks/mitigations.

### Phase 5 — Supporting Docs
- Source material: `.kiro/specs/phase-5-supporting-docs/*`
- Outputs: `BUSINESS_CASE.md`, `DISASTER_RECOVERY_PLAN.md`, `STAFFING_RECOMMENDATION.md`, `SECURITY_REMEDIATION.md`
- Goal: complete executive and operational package.

## Session cadence
1. Re-state current phase and expected deliverable.
2. List known facts and open questions.
3. Produce/revise draft.
4. Run quality gates.
5. Stop for explicit human sign-off.

## Hook parity (manual in Codex)
- Checkpoint reminder: always pause after each phase deliverable.
- Open-questions tracker: maintain a dedicated section and unresolved items list.
- Compliance check: verify regulatory assumptions remain consistent across documents.
