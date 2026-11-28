# Human-in-the-Loop (HITL) PM Prompt Templates

> **Purpose:** Standardize how Agile Project Managers and Scrum Masters pair Generative AI (Gemini / LLMs) with strict legal-analytical verification. Every prompt enforces a **4-Stage HITL Architecture**: `01 Sanitize & Scope (Human)` → `02 Structured Prompting (AI)` → `03 Analytical Verification (Human)` → `04 Compliance Sign-Off (Human)`.

---

## Stage 0: Mandatory Pre-Prompt Sanitization Protocol

Before pasting any notes into an LLM, replace sensitive data using this mapping:

| Raw Data Type | Sanitized Placeholder | Example |
| :--- | :--- | :--- |
| Client / Company Name | `[CLIENT_A]` / `[VENDOR_B]` | `"Acme Corp"` → `"[CLIENT_A]"` |
| Personal Names & Emails | `[ROLE_1]` | `"John Doe (CFO)"` → `"[EXEC_SPONSOR]"` |
| Exact Confidential Revenue | `[METRIC_X]` or rounded % | `"$4,120,450"` → `"[BASELINE_REV]"` |
| Proprietary Code / Keys | `[REDACTED_API]` | Never paste credentials or secrets |

---

## Template 1: Project Charter & Scope Boundaries

**Best for:** Turning raw, sanitized discovery notes into a structured draft Charter with explicit In/Out-of-Scope walls.

```text
Role: Act as a Senior IT & Agile Project Manager specializing in risk-resilient delivery.
Context: Below are sanitized discovery notes for [PROJECT_TYPE] targeting a [DURATION] rollout.
Task: Draft a structured Project Charter containing:
1. Problem Statement & Operational Bottleneck (max 4 bullets)
2. Proposed SMART KPIs table (Metric | Baseline Placeholder | Target | Verification Source)
3. Strict [IN-SCOPE] deliverables vs. [OUT-OF-SCOPE] exclusions to prevent scope creep
4. Top 3 open questions or assumptions that require stakeholder clarification before Sprint 1

Constraints:
- Do NOT invent metrics, budgets, or dates not present in the notes; mark missing data as [VERIFY_WITH_SPONSOR].
- Use concise, executive-ready Markdown tables.

Sanitized Discovery Notes:
[PASTE SANITIZED NOTES HERE]
```

---

## Template 2: Pre-Mortem Risk Register & Mitigation Matrix

**Best for:** Stress-testing a sprint, migration, or rollout plan before kickoff to uncover technical, vendor, and compliance bottlenecks early.

```text
Role: Act as a Principal Delivery Risk Manager with expertise in Agile operations and regulatory compliance.
Context: Below is a sanitized delivery plan for [INITIATIVE_NAME] involving [TEAM_OR_VENDOR_COUNT] workstreams with a target window of [TIMEFRAME].
Task: Conduct a Pre-Mortem analysis assuming the rollout missed its launch window or failed an audit. Generate:
1. Risk Register Markdown table (Risk ID | Category: Tech/Vendor/Compliance/Ops | Root Cause | Probability: L/M/H | Impact: L/M/H | Preventive Mitigation | Contingency Trigger)
2. Top 3 "Silent Killers" (unspoken dependencies or single points of failure implied by the plan)
3. Recommended Go/No-Go readiness gates before production cutover

Constraints:
- Base all operational dependencies strictly on the sanitized input; flag hypothetical assumptions clearly as [ASSUMPTION_TO_VALIDATE].
- Avoid generic advice like "communicate better"—specify concrete controls, buffers, or owners using role placeholders (e.g., [TECH_LEAD], [LEGAL_COUNSEL]).

Sanitized Delivery Plan:
[PASTE SANITIZED PLAN HERE]
```

---

## Template 3: Executive Status Brief & Escalation Memo

**Best for:** Converting granular sprint updates and blocker logs into a 1-minute C-suite readout focused on decisions, trade-offs, and RAG status.

```text
Role: Act as an IT Program Manager preparing a weekly steering committee brief for non-technical executives.
Context: Below are sanitized sprint notes and metrics for [PROGRAM_NAME] (Reporting Period: [SPRINT_OR_WEEK]).
Task: Draft a concise Executive Brief structured as follows:
1. Overall RAG Status ([GREEN / AMBER / RED]) with a 2-sentence bottom-line summary
2. Key Milestones Completed vs. Upcoming Deliverables (max 3 bullets each)
3. Active Blockers & Trade-Off Decisions Required from [EXEC_SPONSOR] (Option A vs. Option B with impact on scope, timeline, or budget)
4. Risk Trend (Improving / Stable / Escalating)

Constraints:
- Strip out low-level engineering jargon; translate technical blockers into business and timeline impact.
- Do NOT soften RED/AMBER statuses or fabricate recovery dates; mark unconfirmed ETAs as [ETA_PENDING_ENG].
- Keep the total output under 250 words.

Sanitized Sprint Notes:
[PASTE SANITIZED NOTES HERE]
```

---

## Template 4: Agile Backlog Decomposition (User Stories & Acceptance Criteria)

**Best for:** Translating ambiguous stakeholder requests into INVEST-compliant User Stories with testable Acceptance Criteria and privacy/compliance flags.

```text
Role: Act as a Senior Agile Project Manager & Scrum Master operating in a regulated IT environment.
Context: Below are sanitized feature notes for [PRODUCT_MODULE] targeted for [SPRINT_OR_RELEASE].
Task: Decompose the request into a sprint-ready backlog draft containing:
1. 3–5 User Stories ("As a [ROLE], I want [CAPABILITY], so that [OUTCOME]")
2. Testable Acceptance Criteria in Given / When / Then format for each story
3. Explicit Technical Dependencies & Compliance/Data Privacy Flags (e.g., PII handling, audit trail, access control)
4. Open ambiguities or edge cases queued for Backlog Refinement

Constraints:
- Do NOT invent business rules, API contracts, or compliance approvals not present in the input; mark missing details as [VERIFY_WITH_PO].
- Keep each story sized to fit within a single sprint (INVEST criteria).
- Output in clean, Jira/GitHub-ready Markdown.

Sanitized Feature Notes:
[PASTE SANITIZED NOTES HERE]
```

---

## Template 5: Meeting Synthesis, Decision Log & Action Plan

**Best for:** Turning raw, sanitized meeting transcripts or retrospective notes into an auditable Decision Log and accountable Action Plan.

```text
Role: Act as an IT Project Operations Lead focused on clear ownership and auditable follow-through.
Context: Below are sanitized notes from a [MEETING_TYPE: e.g., Sprint Review / Stakeholder Sync / Retrospective] for [INITIATIVE_NAME].
Task: Synthesize the discussion into three structured blocks:
1. Confirmed Decisions Log (Decision | Rationale | Decision Owner Placeholder)
2. Action Items Table (Action | Owner Placeholder | Target Date | Dependency / Blocker)
3. Parking Lot & Unresolved Risks requiring follow-up before the next ceremony

Constraints:
- Attribute actions strictly to sanitized role placeholders (e.g., [ENG_LEAD], [PO]); never guess ownership—mark unstated owners as [OWNER_TBD].
- Do NOT hallucinate deadlines; use [DATE_TBD] wherever no explicit date was agreed.
- Remove conversational filler; keep entries concise and verifiable.

Sanitized Meeting Notes:
[PASTE SANITIZED TRANSCRIPT OR NOTES HERE]
```

---

## Stages 3 & 4: Mandatory Human Verification & Compliance Sign-Off

Before any AI-generated draft is shared with stakeholders, pasted into Jira/Confluence, or committed to a client repository, the PM must complete this final gate:

- [ ] **No Hallucinated Facts:** Every metric, date, dependency, and owner placeholder (`[VERIFY_WITH_SPONSOR]`, `[DATE_TBD]`) has been manually verified against source records.
- [ ] **Bias & Tone Audit:** Output uses objective, neutral business language free of speculative blame or unsupported assumptions.
- [ ] **IP & Privacy Hygiene:** No confidential inputs leaked into external prompts, and final outputs comply with internal AI disclosure / EU AI Act transparency rules.
- [ ] **Human Accountability:** The Project Manager assumes full ownership of the final deliverable before distribution.
