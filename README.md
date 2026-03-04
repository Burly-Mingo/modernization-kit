# Legacy Application Modernization Kit for Kiro

An open-source, AI-assisted methodology for modernizing legacy applications — built for [Kiro](https://kiro.dev) and [Claude](https://anthropic.com). Drop this into your Kiro workspace alongside your legacy codebase and let the structured process guide you from assessment to actionable plan.

Designed for multi-application landscapes. Assess each application individually, then analyze them as a whole — shared databases, overlapping business logic, hidden coupling, and consolidation opportunities only become visible when you look at the full picture.

Created by [Burly Mingo LLC](https://burlymingo.com).

## What This Is

A Kiro workspace template that packages a complete modernization methodology as steering files, specs, and hooks. It guides an AI assistant (and the human domain expert working with it) through a structured process that produces real engineering deliverables:

- Per-application architecture assessments with 7 R's classification
- Consolidated cross-application analysis (shared data sources, hidden coupling, consolidation opportunities)
- Prioritized pain point analysis
- Target architecture design with buy vs. build decisions
- Phased modernization plan with timelines and costs
- Business case, DR plan, staffing recommendation, and security remediation plan

Works for a single application, but the methodology is at its best with multiple interconnected applications — that's where the consolidated analysis reveals insights no per-app assessment can surface.

## What This Is Not

- A magic prompt that produces a plan without human input
- A 1:1 code translation tool
- A replacement for domain expertise or professional implementation services
- Tied to any specific source or target technology stack

## Who This Is For

- **Organizations considering modernization** who want a detailed, honest assessment before committing budget. The plan this produces gives you the information to make an informed go/no-go decision.
- **Internal teams planning a modernization** who want a structured process instead of ad-hoc discovery.
- **Organizations hiring a consulting firm** who want to walk into that engagement with a real blueprint — specific enough to hold vendors accountable to scope, timeline, and cost. A detailed plan is leverage at the negotiating table.
- **Consulting firms themselves** who want a repeatable methodology for the assessment and planning phase of modernization engagements.

## How It Works

The methodology has 6 phases, each producing a specific deliverable with a human review checkpoint:

| Phase | What Happens | Deliverable |
|---|---|---|
| 0 - Discovery | Interview about org, industry, regulations, infrastructure, goals | DISCOVERY_SUMMARY.md |
| 1 - Codebase Analysis | AI reads the actual code, produces factual assessment | ASSESSMENT.md (per app) + CONSOLIDATED_ASSESSMENT.md |
| 2 - Pain Points | Interview users about what hurts | PAIN_POINTS.md |
| 3 - Target Architecture | Design the future state (expect multiple revision cycles) | TARGET_ARCHITECTURE.md |
| 4 - Modernization Plan | Phased implementation with timelines, costs, risks | MODERNIZATION_PLAN.md |
| 5 - Supporting Docs | Business case, DR, staffing, security | Multiple documents |

## Quick Start

> **Important:** The `.kiro/` folder must be at the root of the directory you open in Kiro. Kiro looks for `.kiro/steering/`, `.kiro/specs/`, and `.kiro/hooks/` at the workspace root — if `.kiro/` is nested inside a subfolder, Kiro won't see it. All three setup paths below place `.kiro/` at the root of the workspace you'll open.

**Add to an existing project (recommended):**

```bash
# From your project's root directory (where your legacy code lives)
git clone https://github.com/Burly-Mingo/modernization-kit.git /tmp/mod-kit
cp -r /tmp/mod-kit/.kiro .
cp /tmp/mod-kit/MODERNIZATION_METHODOLOGY.md .
rm -rf /tmp/mod-kit
```

Then open the workspace in Kiro. That's it. The steering files activate automatically and the specs appear in the Kiro spec panel.

**Multi-application workspace (optimal):**

```bash
# Create a workspace that contains all related applications
mkdir my-modernization && cd my-modernization
git clone https://github.com/Burly-Mingo/modernization-kit.git /tmp/mod-kit
cp -r /tmp/mod-kit/.kiro .
cp /tmp/mod-kit/MODERNIZATION_METHODOLOGY.md .
rm -rf /tmp/mod-kit

# Add your applications (copy, symlink, or git submodule)
# e.g.:
# cp -r /path/to/app-one ./app-one
# cp -r /path/to/app-two ./app-two
# git submodule add https://repo/app-three ./app-three
# Open my-modernization/ in Kiro (not a parent folder)
```

Having all applications in one workspace lets the AI see shared databases, overlapping stored procedures, cross-app API calls, and data coupling that's invisible when assessing apps in isolation. The consolidated assessment step in Phase 1 depends on this.

**Start fresh (single app):**

```bash
git clone https://github.com/Burly-Mingo/modernization-kit.git my-modernization
cd my-modernization
# Add your legacy codebase to this workspace (copy, symlink, or git submodule)
# Open my-modernization/ in Kiro
```

> **Don't** clone this repo as a subfolder inside another workspace (e.g., `my-project/modernization-kit/`). The `.kiro/` folder would be nested and Kiro won't detect it. Always copy the `.kiro/` folder to the root of whatever directory you open in Kiro.

**What happens when you open in Kiro:**

1. The 4 steering files in `.kiro/steering/` activate automatically — they guide the AI's behavior for the entire engagement (core principles, regulatory awareness, buy vs. build framework, anti-patterns)
2. The 6 specs in `.kiro/specs/` appear in the Kiro spec panel — each one is a phase of the methodology with requirements, design approach, and tasks
3. The 3 hooks in `.kiro/hooks/` provide guardrails — human review reminders, open question tracking, and compliance consistency checks
4. Start a conversation and open the Phase 0 spec. The AI will begin the Discovery Interview.

## What's in the Box

```
.kiro/
├── steering/                              # Always-active AI guidance
│   ├── 00-modernization-principles.md     # Core principles and interaction style
│   ├── 01-regulatory-reference.md         # Compliance framework quick reference
│   ├── 02-buy-vs-build.md                 # Decision framework for component selection
│   └── 03-anti-patterns.md                # What not to do (learned from real projects)
│
├── specs/                                 # Phased workflow with requirements, design, and tasks
│   ├── phase-0-discovery/                 # Organization, industry, regulations, infrastructure, goals
│   ├── phase-1-codebase-analysis/         # Read the code, produce factual assessments
│   ├── phase-2-pain-points/               # Interview users, prioritize what hurts
│   ├── phase-3-target-architecture/       # Design the future state
│   ├── phase-4-modernization-plan/        # Phased implementation plan
│   └── phase-5-supporting-docs/           # Business case, DR, staffing, security
│
└── hooks/                                 # Automated guardrails
    ├── checkpoint-reminder.json           # Pause for human review after each deliverable
    ├── open-questions-tracker.json        # Flag unknowns in deliverables
    └── compliance-check.json              # Validate compliance consistency across documents
```

## Core Principles

- **Modernize, don't translate.** Rethink the architecture, don't just change the language.
- **Containers by default, not by dogma.** Cloud-agnostic is the recommendation, but respect organizational preferences.
- **Buy vs. build at every decision point.** Know the audience — some orgs need vendor support, others embrace open source.
- **AI-assisted, spec-driven development.** Experienced dev + Kiro specs = significantly faster. Not vibe coding.
- **New tech stacks are not the barrier they once were.** AI IDEs let teams adopt the right technology, not just the familiar one.
- **Comprehensive automated testing is a baseline.** AI makes generating unit, integration, and API tests fast enough to be non-negotiable.
- **Honest about unknowns.** "I don't know" is always better than a confident guess.
- **Security is Phase 0.** Fix critical vulnerabilities before modernization begins.
- **The human is always right about their domain.** The AI reads code. The human understands the business.

## Prerequisites

- **[Kiro IDE](https://kiro.dev)** — this kit is built for Kiro's steering files, specs, and hooks. It's the IDE that treats AI-assisted development as a first-class workflow, not a bolted-on autocomplete. The spec-driven development model is what makes this methodology work — structured requirements → design → tasks, with the AI executing and the human reviewing. Other AI IDEs can adapt the methodology (see below), but Kiro is where it shines.
- **Claude Opus 4.6+** (or newer) — the underlying model matters. The codebase analysis, architecture design, and plan generation require a model that can hold large context, reason about complex systems, and produce correct, idiomatic recommendations across multiple languages and frameworks. Claude Opus 4.6 is what this was developed and tested with. Lesser models will produce lesser plans.
- **Codebase access** — the AI needs to read the actual source code
- **A domain expert** — someone who understands the business processes. Reviews every deliverable. This is the irreplaceable ingredient.
- **Time for iteration** — each phase involves analysis → review → correction → revision

## Recommended MCP Servers

These [Model Context Protocol](https://modelcontextprotocol.io/) servers significantly improve the methodology experience in Kiro. None are strictly required, but each one solves a real problem.

**Memory** (`@modelcontextprotocol/server-memory`) — A modernization engagement spans multiple sessions over days or weeks. The Memory MCP maintains a persistent knowledge graph across sessions — discovery findings, regulatory frameworks, architecture decisions, open questions, and cross-application dependencies survive between conversations instead of evaporating. This is the single most impactful MCP for this methodology.

```json
"memory": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-memory"],
  "disabled": false,
  "autoApprove": ["create_entities", "add_observations", "search_nodes"]
}
```

**Sequential Thinking** (`@modelcontextprotocol/server-sequential-thinking`) — Architecture decisions in Phase 3 and plan sequencing in Phase 4 involve complex trade-offs with multiple interacting constraints (compliance, team size, budget, existing infrastructure, cross-app dependencies). Sequential thinking helps the AI reason through these systematically rather than jumping to conclusions.

```json
"sequential-thinking": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"],
  "disabled": false,
  "autoApprove": ["sequentialthinking"]
}
```

**Context7** (`@upstash/context7-mcp`) — When the AI recommends specific technologies (Keycloak, K3s, PostgreSQL, etc.), Context7 lets it pull current documentation rather than relying on training data that may be outdated. Useful during Phase 3 architecture design and Phase 4 when estimating implementation effort.

```json
"context7": {
  "command": "npx",
  "args": ["-y", "@upstash/context7-mcp"],
  "disabled": false,
  "autoApprove": ["resolve-library-id", "query-docs"]
}
```

Add these to `.kiro/settings/mcp.json` (workspace-level) or `~/.kiro/settings/mcp.json` (user-level). Requires `npx` (Node.js). See [MCP documentation](https://modelcontextprotocol.io/) for setup details.

## Adapting This Methodology

This kit is designed for Kiro but the methodology is IDE-agnostic. The steering files are markdown with front-matter that Kiro understands. The specs follow Kiro's requirements/design/tasks structure. The hooks use Kiro's event system. To adapt for another AI IDE:

- Steering files → system prompts or context files
- Specs → task lists or project plans
- Hooks → whatever automation the IDE supports (or manual checkpoints)


## Codex Compatibility (No Fork Required)

This kit now includes a `.codex/` compatibility layer so you can run the same methodology in Codex without forking the repo.

- Kiro uses `.kiro/` (steering/specs/hooks)
- Codex uses `.codex/` (system instructions/runbook/quality gates)
- Both produce the same deliverables in the workspace root

Start with `.codex/README.md`, then load `.codex/context/system-instructions.md` and follow `.codex/runbooks/phase-workflow.md`.

## Origin Story

This methodology was developed by [Burly Mingo LLC](https://burlymingo.com) during a real modernization engagement — three legacy ASP.NET WebForms applications (VB.NET + C#, .NET 4.5-4.7, 9 SQL Server databases) being modernized to a unified platform (ASP.NET Core 9, React/Next.js, PostgreSQL, Redis, K3s). The entire process was conducted in Kiro IDE with Claude Opus 4.6, producing a 1,600-line modernization plan, business case, DR plan, staffing recommendation, and security assessments over 12+ collaborative sessions.

The key insight: the plan's quality came from iteration and domain expertise, not from a clever prompt. Every time the human corrected the AI ("Not Blazor — React." "EF Core alone won't cut it." "You need Redis for this workflow."), the plan got dramatically better. Kiro's spec-driven workflow made this iteration structured and productive rather than chaotic.

A second insight emerged from having all three applications in one workspace: assessing them individually produced useful findings, but assessing them together revealed shared databases, overlapping stored procedures, cross-app data dependencies, and consolidation opportunities that no single-app assessment could surface. The multi-app consolidated analysis fundamentally changed the migration strategy, timeline, and data architecture. This kit packages both insights — the iterative human-in-the-loop process and the multi-app holistic analysis — so others can follow them.

## License

MIT. Use it, fork it, improve it, sell consulting services around it. Just don't pretend a prompt alone produces a good modernization plan — the human in the loop is what makes it work.

Built with [Kiro](https://kiro.dev) + [Claude Opus 4.6](https://anthropic.com). If you're modernizing legacy systems without spec-driven AI-assisted development, you're working too hard.

---

*A [Burly Mingo LLC](https://burlymingo.com) open source project.*
