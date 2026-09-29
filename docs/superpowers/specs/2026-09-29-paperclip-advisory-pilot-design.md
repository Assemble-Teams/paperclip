# Paperclip Advisory Pilot — Lean Design

Status: Approved by founder  
Date: 2026-09-29  
Branch: `feat/advisory-control-plane-foundation`  
Audience: Founder, product, engineering, ATLAS/RAS operators

## 1. Decision

Build the advisory operating system now, but do not build the full SaaS product now.

Paperclip remains the private control plane and AI-workforce coordinator. Google Workspace remains the practical business-working environment. The proprietary Assemble Teams layer is the advisory methodology, skills, routines, evidence model, outcome data, and engagement operating practices.

The pilot must optimize for one question:

> Can Uday run several advisory engagements more effectively, with stronger evidence, better follow-through, and better outcomes, using Paperclip plus Google Workspace?

External customer/provider product access is deferred until repeated project evidence shows which workflows deserve productization.

## 2. Scope discipline

### Build / configure now

- Private authenticated Paperclip interface for Uday
- ATLAS operating role
- RAS assurance role
- Growth operating role
- Delivery operating role
- Advisory project template
- Provider/customer/partner organization records needed for the pilot
- Advisory Ledger
- Qualification workflow
- Meeting-to-decision/action workflow
- Transformation backlog
- Outcome Ledger
- Weekly engagement review
- Formal engagement/project closure and retrospective
- Google Drive/Docs/Sheets/Calendar/Gmail usage where it materially reduces manual work
- Existing Paperclip approvals, tasks, skills, routines, artifacts, audit, budgets, and Apps infrastructure

### Explicitly defer

- WhatsApp Business integration
- Facebook Messenger integration
- Hugging Face deployment
- Public self-service registration
- Customer portal
- Provider portal
- Public scheduling
- Public SaaS billing
- Custom multi-tenant client UX
- Full CRM replacement
- Separate messaging product
- Extensive custom dashboards before real usage evidence
- Heavy fork-specific rewrites of Paperclip core

These items may return after the pilot; they are not rejected permanently.

## 3. Product boundary

The first product is Uday's private advisory control room.

Paperclip owns:
- work
- issues
- projects
- goals
- approvals
- agent runs
- skills
- routines
- artifacts
- budgets/costs
- audit/activity
- governed tool access

Google Workspace owns:
- email
- calendar events
- Drive documents
- Docs
- Sheets
- intake forms where useful

The pilot should not duplicate capabilities already implemented well in either system.

## 4. Human operating model

Uday is the primary human operator during the pilot.

Clients and providers interact through normal business channels and shared Google artifacts. They do not receive Paperclip access during the first phase.

The operating lifecycle is:

1. Submission or introduction
2. Team review
3. Qualification
4. Direct advisory or partner path
5. Discovery
6. Engagement outcome definition
7. Project / 90-day plan
8. Meetings and evidence collection
9. Decisions and actions
10. Delivery / transformation execution
11. Outcome measurement
12. Closure
13. Retrospective
14. Methodology improvement

Every meaningful project object should trace to an intended outcome.

## 5. Qualification policy

Qualification rules are internal guidance, not customer-facing judgments.

The exact qualification thresholds are private operating policy and must not be committed to this public repository. They are stored in the private Paperclip company configuration / Skill Studio and may be revised without code changes.

Meeting the private qualification baseline does not automatically grant a consultation.

External language remains polite, respectful, and suggestive. Possible internal dispositions include:
- direct advisory review
- additional information required
- partner path
- future fit
- not currently aligned

Startups should ordinarily be evaluated for a partner-led path when that better fits their stage and needs.

Direct access to Uday's calendar remains invitation-only after review. Exact availability rules are private runtime configuration and are not published in this repository.

## 6. Advisory Ledger

Use a tightly controlled Google Sheet for pilot-stage business tracking instead of building a full CRM.

Minimum tabs:

### Organizations
- organization
- roles: provider / customer / partner / prospect / referral partner
- operating history
- revenue band / MRR where relevant
- industry / geography
- relationship owner
- current status

### People
- person
- organization
- role/title
- relationship context
- contact details
- last interaction
- next action

### Opportunities
- organization
- opportunity
- problem/outcome
- estimated project value
- source
- stage
- next action
- expected decision date
- direct advisory / partner path

### Engagements
- organization
- engagement objective
- scope
- start / target end
- current phase
- project links
- commercial notes/reference

### Meetings & Actions
- meeting
- organization/project
- decisions
- actions
- owner
- due date
- risks
- evidence links

### Outcomes
- metric
- baseline
- target
- current result
- measurement method
- evidence/source
- date
- confidence

The Ledger is a controlled pilot instrument, not a permanent system-of-record decision. Repeated friction determines which fields later move into Paperclip/Postgres.

## 7. AI operating team

Keep the initial AI workforce small.

### ATLAS — Chief of Staff / Intelligence
Responsibilities:
- prepare daily/weekly briefs
- synthesize project context
- identify changes and constraints
- propose next actions
- summarize relevant evidence
- maintain relationship and engagement context
- draft, never silently authorize, consequential actions

### RAS — Assurance
Responsibilities:
- challenge unsupported conclusions
- verify evidence
- inspect deliverables
- detect missing requirements
- check closure preconditions
- test whether "built", "wired", and "proven" are actually distinct
- escalate uncertainty rather than hiding it

### GROWTH — Relationships & Commercial
Responsibilities:
- prospect / opportunity follow-up
- qualification support
- introduction tracking
- proposal support
- next-action discipline
- partner routing
- commercial pipeline summaries

### DELIVERY — Engagement Operations
Responsibilities:
- project setup
- milestones
- actions
- blockers/dependencies
- meeting follow-up
- risk tracking
- outcome measurement
- closure coordination

Additional expertise such as DevSecOps, finance, GCC, architecture, talent, customer success, and solution engineering should begin as skills. Promote a skill into a permanent agent only when repeated workload justifies separate context, routines, and budget.

## 8. Skills are the proprietary methodology layer

Prioritize skills over custom application code.

Because this repository is public, proprietary advisory skills, live client/provider identities, private commercial thresholds, calendar rules, and engagement evidence must remain outside git. Store them in the private Paperclip company Skill Studio, private runtime configuration, or approved private Google Workspace assets. Public repository content may include only generic scaffolding and non-sensitive examples.

Initial skill candidates:
- advisory-discovery
- company-intake
- established-company-qualification
- startup-partner-routing
- provider-assessment
- enterprise-readiness
- gcc-readiness
- project-health
- meeting-intelligence
- proposal-review
- customer-success
- outcome-measurement
- closure-retrospective
- ras-verification

Each skill should contain:
- purpose
- inputs
- evidence expectations
- procedure
- output contract
- escalation conditions
- tone/communication rules
- prohibited autonomous actions
- verification criteria

## 9. Pilot Provider A / Project #1 operating template

The first pilot project should run end-to-end inside Paperclip.

Suggested project structure:

### Outcome
Improve enterprise readiness, commercial capability, delivery confidence, and readiness to win/deliver higher-value US engagements.

### Initial workstreams
- Executive
- Growth / Sales
- Delivery
- Engineering / DevSecOps
- Talent

### Paperclip objects
- project goal
- workstream milestones
- issues/actions
- evidence artifacts
- decisions/comments
- approvals where consequential
- outcome measures
- retrospective

Do not create a custom dashboard solely for the first pilot provider before we learn which information Uday repeatedly needs.

## 10. Weekly operating cadence

### Before meetings
ATLAS prepares:
- context
- previous commitments
- open actions
- risks
- relevant evidence
- questions needing decisions

### After meetings
DELIVERY drafts:
- decisions
- actions
- owners
- deadlines
- risks
- evidence requests

ATLAS updates the engagement narrative and proposes next actions.

RAS challenges:
- unsupported claims
- missing evidence
- ambiguous ownership
- weak completion criteria
- privacy/permission risks

Uday approves or corrects consequential outcomes.

### Weekly review
Paperclip should help Uday answer:
- What changed?
- What needs my decision?
- What is blocked?
- Which relationship needs attention?
- Are we moving toward the agreed outcomes?
- What did we learn that should change the methodology?

## 11. Outcome Ledger

Every engagement must establish measurable baseline(s), target(s), and actual result(s).

Preferred classes:

### Time
- audit completion time
- proposal turnaround
- hiring time
- issue resolution
- delivery lead time

### Revenue
- qualified pipeline
- win rate
- average contract value
- expansion revenue
- revenue per customer

### Economics
- gross margin
- utilization
- bench cost
- delivery variance

### Quality
- defects
- delays
- incidents
- customer escalations

### Capability
- sales maturity
- delivery maturity
- engineering maturity
- security readiness
- talent readiness

A project is not considered a successful product-learning event merely because people used Paperclip. We need evidence of operating improvement, advisory efficiency, or better decision quality.

## 12. Closure discipline

Every engagement/project should close through:

1. deliverables complete
2. open issues reviewed
3. agreed acceptance/closure state
4. outcome measures updated
5. financial/commercial status captured where relevant
6. lessons learned
7. methodology changes proposed
8. RAS evidence check
9. archive / future opportunity decision

Retrospectives should identify:
- what worked
- what failed
- where Uday created leverage
- where the provider/customer struggled
- which repeated friction deserves automation
- which automation did not create value
- which skill/template should change

## 13. Engineering doctrine

### Keep the fork thin
Prefer:
- configuration
- agent definitions
- skills
- routines
- templates
- small plugins
- additive business-domain extensions

Avoid:
- replacing working Paperclip core
- duplicating upstream Apps/auth/approvals/audit infrastructure
- large UI rewrites without repeated operational evidence
- divergence that makes upstream synchronization difficult

### Productization trigger
Custom software is justified when the same material workflow friction appears repeatedly across real engagements and cannot be solved safely with Paperclip configuration, skills, Google Workspace, or a small plugin.

## 14. Security and authority

During the pilot:
- Uday remains primary human operator
- external Paperclip access is disabled by default
- consequential external communications require human review
- AI may analyze, draft, recommend, classify, and prepare
- AI may not autonomously sign agreements, change commercial commitments, approve final deliverables, grant external access, expose confidential information, or close an engagement
- secrets remain in approved secret storage
- all material AI work should remain attributable to agent/run/task context
- private provider/customer information must not leak between engagements

## 15. Deferred integrations

WhatsApp Business and Facebook Messenger are explicitly deferred until the end of the project/pilot unless the founder reopens the decision.

Hugging Face remains a possible later research/demo/distribution surface, not the operational hosting target.

These deferred items should not influence the pilot data model or UI except where a future-neutral abstraction is essentially free.

## 16. Pilot sequence

### Project 1
Run one provider transformation engagement heavily through the system. Optimize for learning, not automation.

### Project 2
Run a second provider. Test whether the methodology generalizes.

### Project 3
Run a real customer project with provider participation. Test the complete commercial-to-delivery loop.

### Projects 4–10
Gradually shift from:
- Uday drives system
- system assists Uday
- system guides repeatable work
- provider/customer collaboration can be selectively exposed
- Uday increasingly intervenes strategically

External Paperclip access should be considered only after this evidence exists.

## 17. Graduation criteria

The lean pilot graduates to productization discussion when most of the following are true:

- 3–5 engagements run materially through Paperclip
- Uday uses the system weekly without maintaining a shadow process elsewhere
- meeting-to-action capture is reliable
- qualification / partner routing is operationally useful
- Outcome Ledger contains credible baseline/result evidence
- RAS catches real quality/evidence problems
- repeatable advisory skills exist
- at least two organizations demonstrate the methodology generalizes
- specific external collaboration needs repeat across engagements
- custom software opportunities are supported by repeated friction, not preference

A broader external beta should not begin solely because the software is technically capable of multiple users.

## 18. Success definition

The first success state is not "Paperclip is a SaaS."

It is:

> Uday can run advisory work through one disciplined system, AI agents materially reduce coordination and analysis burden, evidence and outcomes improve decision quality, and repeated project learning makes the methodology stronger.

If that is proven, the future product can be designed from evidence rather than assumptions.