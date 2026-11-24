# Evidence-Based Retrospective & Action Tracker

> **Purpose:** Turn post-sprint and post-pilot retrospectives into measurable operational improvements. Rather than collecting unactionable opinions, this framework maps empirical signals and KPI variance to root causes, named owners, and permanent SOP updates.

---

## 1. Review Control & Context

| Field | Details |
| :--- | :--- |
| **Initiative / Sprint / Pilot** | `[e.g., Phase 1 Pilot Rollout / Sprint 14]` |
| **Facilitator (PM / Scrum Master)** | `[Name]` |
| **Participants** | `[Product, Engineering, Operations, Frontline Leads]` |
| **Review Date** | `YYYY-MM-DD` |
| **Next Audit Checkpoint** | `[e.g., Sprint 15 Mid-Point / Pilot Week 2]` |

---

## 2. Quantitative & Qualitative Signal Intake

Anchor the retrospective in verified data before opening discussion.

| Metric / Signal | Baseline | Target | Actual Result | Variance | Primary Data Source |
| :--- | :---: | :---: | :---: | :---: | :--- |
| **Delivery / Cycle Time** | `[e.g., 90 min]` | `[e.g., 60 min]` | `[Actual]` | `[+/- %]` | Analytics / Jira |
| **Defect / Error Rate** | `[e.g., 8%]` | `[e.g., < 2%]` | `[Actual]` | `[+/- %]` | QA / Incident Logs |
| **Adoption / CSAT Score** | `[e.g., 72%]` | `[e.g., ≥ 85%]` | `[Actual]` | `[+/- %]` | User / Staff Survey |
| **Budget / Effort Burn** | `[Planned]` | `[≤ Planned]` | `[Actual]` | `[+/- %]` | Finance / Time Logs |

---

## 3. Signal → Root Cause Matrix

Separate surface symptoms from underlying systemic blockers (*5 Whys* approach).

| ID | Observed Signal (What Happened) | Domain | Root Cause Analysis (Why It Happened) | Impact on Velocity / P&L |
| :--- | :--- | :--- | :--- | :--- |
| **S-01** | `[e.g., Recurring handoff delays between teams during peak load]` | Process | `[e.g., Ambiguous Definition of Ready and missing escalation SLA]` | High — delayed cycle time |
| **S-02** | `[e.g., Edge-case UI friction causing manual workarounds]` | Technical / UX | `[e.g., Frontline operators were not included in early staging UAT]` | Medium — elevated error rate |
| **S-03** | `[e.g., Last-minute compliance rework before release]` | Governance | `[e.g., Legal/IP review triggered in Sprint N instead of Sprint 0]` | Critical — launch delay risk |

---

## 4. Committed Action Tracker

Every action item must have **one named owner**, a **hard due date**, and an **objective verification method**. Limit active improvement items to **3–5 per cycle** to ensure completion.

| Action ID | Linked Signal | Concrete Action Item | Owner | Due Date | Verification Criteria (Done Means...) | Status |
| :--- | :---: | :--- | :--- | :--- | :--- | :---: |
| **ACT-01** | `S-01` | Update Definition of Ready checklist in Jira and enforce pre-sprint triage | `[Name]` | `YYYY-MM-DD` | 100% of Sprint N+1 tickets pass DoR gate | `Open` |
| **ACT-02** | `S-02` | Add 2 frontline champions to staging UAT 5 days prior to release | `[Name]` | `YYYY-MM-DD` | UAT sign-off logged before deployment | `In Progress` |
| **ACT-03** | `S-03` | Embed mandatory Sprint 0 Compliance & IP Gate into kickoff template | `[Name]` | `YYYY-MM-DD` | Gate audited in next Project Charter | `Done` |

---

## 5. Institutionalizing Improvements (SOP Lock-In)

Prevent solved issues from recurring in future projects or teams:
- [ ] Updated core runbooks / SOPs in Notion or Confluence
- [ ] Added newly discovered failure modes to `agile-delivery/pre-mortem-risk-register.md`
- [ ] Shared executive summary (wins, trade-offs, and locked fixes) with stakeholders
- [ ] Scheduled 30-day follow-up check to confirm KPI gains held steady
