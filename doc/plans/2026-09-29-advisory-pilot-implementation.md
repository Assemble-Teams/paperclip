# Paperclip Advisory Pilot — Implementation Plan

Status: Approved for execution  
Date: 2026-09-29  
Design source: `docs/superpowers/specs/2026-09-29-paperclip-advisory-pilot-design.md`  
Branch: `feat/advisory-control-plane-foundation`

## 1. Implementation objective

Deliver the smallest usable private advisory operating system for Uday without turning the public Paperclip fork into a bespoke SaaS platform.

The implementation should prove five things:

1. Uday can operate from a private authenticated Paperclip interface.
2. A four-role AI operating team can coordinate advisory work with clear authority and evidence.
3. A real pilot engagement can move from discovery through actions, outcomes, and closure.
4. Google Workspace can remain the practical business-working layer without duplicating it inside Paperclip.
5. Repeated friction, not speculative architecture, determines future custom software.

## 2. Non-negotiable constraints

- Keep the upstream Paperclip core thin and mergeable.
- Do not put live client/provider names, private qualification thresholds, calendar availability, commercial terms, credentials, or proprietary advisory playbooks in this public repository.
- WhatsApp Business and Facebook Messenger stay deferred.
- Hugging Face stays deferred.
- No customer/provider portal in this implementation.
- No public scheduling.
- No custom CRM application.
- No UI overhaul unless a pilot workflow proves the existing UI materially inadequate.
- AI can draft/recommend/analyze; consequential authority remains human-controlled.
- Preserve Paperclip invariants: company scope, atomic issue checkout, approvals, budgets, activity logging, skills, routines, and governed tools.

## 3. Reuse map

### Use unchanged from Paperclip
- authenticated/private deployment mode
- company model
- projects/goals/issues/comments
- human board/admin model
- agent registry and reporting lines
- heartbeat execution
- approvals and review policies
- routines
- cost/budget tracking
- activity/audit trail
- Skill Studio / company skill library
- Apps / governed connector infrastructure
- Google Workspace connector architecture
- artifacts/work products
- secrets manager
- tests and eval surfaces

### Add as thin public scaffolding
- one optional advisory team template with four generic roles
- one generic advisory project template
- one weekly review routine
- documentation/runbook for private runtime configuration
- validation tests for the new team template

### Keep private at runtime
- detailed ATLAS/RAS/GROWTH/DELIVERY methodology prompts beyond generic role contracts
- qualification thresholds
- real organizations and contacts
- opportunity values and commercial terms
- actual consultation availability
- provider/customer evidence
- project notes
- Outcome Ledger values
- Google credentials and tokens

## 4. Public repository structure to add

Create one optional team catalog entry:

`packages/teams-catalog/catalog/optional/advisory/advisory-pilot/`

Expected files:

```text
advisory-pilot/
├── TEAM.md
├── agents/
│   ├── atlas/AGENTS.md
│   ├── ras/AGENTS.md
│   ├── growth/AGENTS.md
│   └── delivery/AGENTS.md
└── projects/
    └── advisory-operations/
        ├── PROJECT.md
        └── tasks/
            └── weekly-advisory-review/
                └── TASK.md
```

Do not add proprietary skills to `packages/skills-catalog` in this phase. The private company Skill Studio is the correct initial home for the advisory methodology.

## 5. Team template contract

### TEAM.md

Use:
- schema: `agentcompanies/v1`
- category: `advisory`
- key: `paperclipai/optional/advisory/advisory-pilot`
- defaultInstall: `false`
- manager: `agents/atlas/AGENTS.md`
- include RAS, GROWTH, DELIVERY, project template
- tags limited to generic advisory/operations terms
- no external-source or script requirements
- no private thresholds or client references

The template should remain `markdown_only` trust where possible.

### ATLAS

Public role contract:
- chief-of-staff / intelligence coordinator
- owns synthesis, context, prioritization, delegation, briefs, and decision preparation
- reports to human board
- cannot approve consequential actions
- delegates assurance to RAS and specialty work to the appropriate role
- must preserve evidence/provenance and label uncertainty

### RAS

Public role contract:
- independent assurance and evidence reviewer
- should not be the primary producer of the artifact it verifies where practical
- checks requirements, evidence, completion criteria, unsupported claims, and risk
- adverse findings are valid completed review outputs
- cannot silently change commercial or access state

### GROWTH

Public role contract:
- opportunity/relationship operating role
- prepares follow-up, qualification summaries, partner-path suggestions, and proposal inputs
- keeps next actions explicit
- does not promise work, pricing, or availability externally without human approval

### DELIVERY

Public role contract:
- engagement operations
- converts meetings and project context into decisions/actions/risks
- tracks owners, due dates, blockers, and outcomes
- prepares closure state but does not close consequential engagements autonomously

## 6. Generic project template

`projects/advisory-operations/PROJECT.md` should be generic enough for any provider/customer engagement.

Purpose:
- hold advisory work that traces to an explicit outcome
- support meeting notes, issues/actions, evidence, decisions, approvals, and outcomes
- avoid naming any real organization

The project description should instruct operators to create engagement-specific projects from this template rather than storing multiple unrelated clients in one shared project.

## 7. Weekly review routine

Add a recurring task owned by ATLAS:

`projects/advisory-operations/tasks/weekly-advisory-review/TASK.md`

The public routine asks ATLAS to review:
- changed context
- open actions
- blocked work
- decisions requiring the board
- evidence gaps
- relationship/opportunity follow-up
- outcome movement
- methodology-learning candidates

It must not encode exact client data, private thresholds, or proprietary scoring rules.

Timer scheduling may remain disabled by import if that is the existing catalog portability behavior. The private instance can configure the desired cadence after installation.

## 8. Private instance bootstrap

This is an operator/runtime step, not public repository content.

### Deployment profile

Use Paperclip:
- runtime mode: `authenticated`
- exposure: `private`
- reachability: `tailnet` preferred for the pilot, or `lan`/private reverse proxy if needed
- first human admin: Uday
- external self-registration: disabled/not exposed
- production customer/provider access: none during phase 1

The existing deployment contract supports authenticated/private operation and private-network reachability; do not build a new auth stack.

### Company

Create a private company/operating entity for the advisory pilot. The runtime company name is an operator choice and does not need to be committed.

### Team

Install/import the optional advisory-pilot team and select available model/runtime adapters at install time rather than hard-coding model vendors in TEAM.md.

Initial model assignment is provisional. RAS/evals should determine later routing.

## 9. Private skills to create in Skill Studio

Create the first six private skills before expanding to the longer skill backlog:

1. `advisory-discovery`
2. `qualification-routing`
3. `meeting-intelligence`
4. `outcome-measurement`
5. `closure-retrospective`
6. `ras-verification`

Each private skill must include:
- purpose
- allowed inputs
- evidence expectations
- procedure
- output contract
- uncertainty handling
- human approval conditions
- communication-tone rules
- prohibited autonomous actions
- verification checklist

### Private skill data

The following stay in private runtime configuration/skills:
- established-company qualification thresholds
- startup partner-routing specifics
- exact consultation availability
- proprietary assessment questions
- partner preferences
- project economics rules
- provider/customer names

Use Paperclip's company-managed Skill Studio / `create_skill` path so these instructions remain instance/company-scoped rather than public git content.

## 10. Advisory Ledger

Do not add a database CRM module in this implementation.

Create one private Google Sheet with these tabs:
- Organizations
- People
- Opportunities
- Engagements
- Meetings & Actions
- Outcomes

Use the design specification as the field guide. Keep it deliberately small.

### Integration rule

For the first pilot:
- manual or controlled operator updates are acceptable
- do not build bidirectional sync before repeated friction exists
- link Sheet/Drive artifacts into Paperclip projects when useful
- the sheet is not exposed publicly
- no autonomous financial/account updates

### Trigger for later schema promotion

A ledger concept moves into Paperclip/Postgres only when at least one of these is true:
- the same update must happen in two places repeatedly
- authorization/audit needs exceed Sheets
- automation needs reliable machine-readable state
- multi-user editing creates conflicts
- a workflow cannot be safely validated in Sheets
- the data becomes essential to productized external collaboration

## 11. Google Workspace setup

Use existing Paperclip Apps/connectors where current support is sufficient.

Pilot priority:
1. Drive
2. Docs/Sheets
3. Calendar
4. Gmail

Do not enable broad scopes merely because they are available.

### Drive
Create private engagement folders using a lightweight convention such as:
- Working
- Meetings
- Evidence
- Deliverables
- Archive

### Calendar
Calendar remains meeting source-of-truth. Exact consultation availability remains private.

### Gmail
Start read/draft-first. External sending remains human-reviewed during the pilot.

### Forms
Use Google Forms only where a structured intake materially improves the workflow. Do not build a native forms product.

## 12. Project #1 runtime setup

Project #1 is created only in the private Paperclip instance.

The public repository must refer to it generically as Pilot Provider A.

Private runtime project structure:

- engagement outcome
- current constraints
- five initial workstreams:
  - Executive
  - Growth / Sales
  - Delivery
  - Engineering / DevSecOps
  - Talent
- milestone(s) with explicit success criteria
- issue/action backlog
- evidence artifacts
- decision trail
- outcome measures
- closure/retrospective task

Do not build a custom provider dashboard.

## 13. Meeting workflow

### Before meeting
ATLAS produces a brief from available authorized context:
- previous commitments
- open actions
- changed context
- risks
- evidence gaps
- questions needing decisions

### After meeting
DELIVERY drafts:
- decisions
- actions
- owners
- due dates
- risks
- evidence requests

### Assurance
RAS reviews the draft for:
- unsupported claims
- missing evidence
- ambiguous ownership
- weak completion criteria
- confidential information leakage
- consequential actions that need human approval

### Human gate
Uday approves/corrects important decisions and external follow-up.

In phase 1, this can be a documented operating routine using existing Paperclip tasks/comments/artifacts. Do not build a dedicated meeting microservice.

## 14. Outcome workflow

Every pilot project should define at least one meaningful outcome metric.

Each metric records privately:
- definition
- baseline
- target
- current result
- measurement date
- source/evidence
- confidence/limitations

ATLAS may summarize movement.
RAS checks whether the claimed movement is actually supported.
Uday decides what can be stated externally.

## 15. Closure workflow

Use existing issues/approvals/artifacts to enforce a closure checklist:

- deliverables addressed
- remaining risks dispositioned
- open actions resolved or intentionally transferred
- outcomes updated
- commercial state reviewed where relevant
- lessons learned captured
- methodology improvements proposed
- RAS verification completed
- human closure decision recorded

Do not build a custom state machine in the database in this phase unless operating evidence shows the issue/approval model cannot support it safely.

## 16. Public repo privacy hardening

Before implementation PR is ready:

- search the branch for real client/provider identifiers introduced by our advisory changes
- search for private commercial thresholds
- search for exact personal scheduling rules
- search for phone numbers, emails, credentials, tokens, or Google file identifiers
- ensure no proprietary Skill Studio content has been copied into git
- ensure examples use synthetic names

This is a RAS blocking check.

## 17. Tests and verification

### Catalog checks
Run:
```sh
pnpm --filter @paperclipai/teams-catalog validate
pnpm --filter @paperclipai/teams-catalog test
```

Update/add tests only if the new optional team exposes a catalog edge not already covered.

### Targeted repository checks
Run the smallest relevant tests while implementing.

### PR-ready checks
Before hand-off:
```sh
pnpm -r typecheck
pnpm test:run
pnpm build
```

If any command cannot be run, report it explicitly.

### Manual acceptance
Verify in an isolated/private Paperclip instance:
- optional team appears in team catalog/import flow
- import preview shows exactly four agents, one project, and one weekly routine
- no model vendor is hard-coded where import-time choice is supported
- Uday can sign in as instance admin
- external user access is not enabled
- ATLAS can receive/own a task
- DELIVERY can own an action-oriented task
- RAS can independently review work
- GROWTH can hold commercial/relationship work
- review/approval gates work for consequential actions
- activity/run attribution is visible
- private skills are accessible only inside the intended company
- Google connectors, when enabled, use least privilege

## 18. RAS acceptance scenarios

RAS should reject the pilot as "proven" unless all applicable scenarios pass:

1. Public git contains no live client/provider confidential configuration.
2. A generic team install creates the intended four-role hierarchy.
3. An agent cannot treat a suggestion as human approval.
4. RAS can return an adverse verdict without the work disappearing.
5. A task has a clear owner and source/outcome context.
6. A meeting-derived action remains a draft until the operator accepts consequential state.
7. A private skill remains company-scoped.
8. Google access can be revoked without breaking unrelated Paperclip auth.
9. The first pilot project can be operated without a custom dashboard.
10. A closure review captures outcomes and lessons before project completion is treated as complete.

## 19. Minimal task graph for execution

Follow Paperclip's "fewest tasks" planning rule.

| Task | Owner | Initial state | Blocker | Why it is separate |
|---|---|---|---|---|
| A. Add generic advisory team template + catalog validation | Engineering/Codex | ready | none | Public repo deliverable with code/catalog verification |
| B. RAS privacy/security review of branch | RAS/reviewer | blocked | A | Independent review boundary |
| C. Bootstrap private instance + company + private skills + Google pilot setup | Uday/ATLAS with operator support | blocked | B | Requires private runtime/credentials and cannot live in public git |
| D. Run Project #1 and collect operating evidence | Uday + ATLAS/DELIVERY/GROWTH | blocked | C | Real engagement lifecycle |
| E. Pilot retrospective + productization decision | Uday + RAS | blocked | D | Independent outcome/learning gate |

Do not split A into one task per file/agent. One engineering owner should implement and verify the complete team template.

## 20. Commit strategy

Implementation should stay easy to review and easy to revert.

Suggested commits:

1. `feat: add generic advisory pilot team template`
2. `test: validate advisory pilot catalog entry` only if a dedicated test change is needed
3. `docs: add private advisory pilot operator runbook` if a non-sensitive runbook is useful
4. privacy/assurance fixes resulting from RAS review

Do not mix unrelated upstream cleanup into this branch.

## 21. Pull request gate

After implementation and private-data review:
- read `.github/PULL_REQUEST_TEMPLATE.md`
- use every required section
- include Thinking Path, What Changed, Verification, Risks, Model Used, Checklist
- open PR from `feat/advisory-control-plane-foundation` to `master`
- do not merge automatically unless the founder explicitly authorizes merge

## 22. What "done" means for this implementation

The implementation is done when:

- the public fork contains only generic advisory scaffolding, not proprietary operating details
- a private authenticated Paperclip instance can be operated by Uday
- the four-role AI team is installable/configurable
- private skills hold the actual advisory methodology
- one generic advisory project/routine is available
- Project #1 can run using existing Paperclip work objects plus Google Workspace
- Outcome and closure discipline are operational
- RAS evidence shows the setup is wired and usable
- no deferred integration has been pulled back into scope

Only after the first real project exposes repeated friction should we decide whether to add application schema, custom UI, portals, or additional integrations.