# SOP: AI Tool Evaluation, Radar & Safe Adoption

**Document ID:** AI-GOV-SOP-02  
**Owner:** Maryna Denysenko (Agile Project Operations & AI Governance)  
**Status:** Active | **Review Cadence:** Quarterly  
**Alignment:** EU AI Act Risk Tiers • NIST AI RMF • Google PAIR (People + AI Guidebook)

---

## 1. Purpose & Scope

Generative AI tools evolve weekly, creating two competing operational risks for delivery teams: falling behind on productivity gains, or adopting unvetted tools (**Shadow AI**) that expose proprietary data, breach IP compliance, or bloat SaaS budgets.

This Standard Operating Procedure (SOP) establishes a repeatable, lightweight governance workflow for:
1. Monitoring emerging AI capabilities without information overload (**Technology Radar**).
2. Scoring candidate tools objectively before granting team access (**4-Pillar Evaluation Matrix**).
3. Running time-boxed pilots on sanitized data (**2-Week Sandbox Protocol**) to reach an auditable **Adopt / Hold / Reject** decision.

---

## 2. Continuous AI Monitoring (Technology Radar)

Instead of ad-hoc trend chasing, AI monitoring follows a structured cadence anchored in verified primary sources:

| Cadence | Focus Area | Verified Primary Sources | Output |
| :--- | :--- | :--- | :--- |
| **Weekly (30 min)** | Platform updates, workflow capabilities, and practical case studies | Official Vendor Release Notes (Google Gemini / Workspace AI), curated industry analysis (e.g., *Hard Fork*, PMI AI updates) | Shortlist of 1–2 relevant capabilities logged in the Backlog |
| **Monthly (1 hr)** | Responsible AI patterns, UX & Human-in-the-Loop (HITL) design | Google PAIR (*People + AI Guidebook*), OWASP Top 10 for LLMs | Updates to internal prompt sanitization & HITL checklists |
| **Quarterly (2 hrs)** | Regulatory shifts, vendor policy changes, and tool stack audit | EU AI Office updates, NIST AI RMF guidance, SaaS vendor ToS/DPA updates | Sunset underused tools; re-verify compliance of active stack |

---

## 3. 4-Pillar Evaluation Matrix (Pre-Pilot Gate)

Before any AI tool enters a team sandbox, the Project Manager scores it across four weighted criteria (scale `1` = Poor to `5` = Strong).

| Pillar | Weight | Key Evaluation Questions | Hard Veto Condition |
| :--- | :---: | :--- | :--- |
| **1. Data Privacy, Security & IP** | **35%** | Does the vendor guarantee zero training on business inputs? Are GDPR/SOC2 controls and opt-out toggles available? What is the EU AI Act risk classification? | **VETO:** Vendor retains rights to train on user data with no enterprise opt-out, or lacks clear data residency terms. |
| **2. Delivery Value & ROI** | **30%** | Does it solve a recurring delivery bottleneck (e.g., backlog refinement, risk analysis, documentation) with measurable time savings per sprint? | None |
| **3. Workflow Integration** | **20%** | Does it integrate cleanly with the existing delivery stack (Jira, Notion, GitHub, Google Workspace) without creating copy-paste friction? | None |
| **4. Commercial & Lock-in Risk** | **15%** | Is pricing predictable at team scale? Can outputs, prompts, and context be exported cleanly if we switch vendors? | None |

### Decision Thresholds
* **Pass to Sandbox (Weighted Score $\ge$ 3.8 & Zero Vetoes):** Approved for a 2-week controlled pilot.
* **Watchlist / Hold (Score 3.0 – 3.7):** Promising capability, but immature security or unclear ROI; revisit next quarter.
* **Reject (Score < 3.0 or Any Hard Veto):** Do not test; log rationale in the Decision Register to prevent duplicate requests.

---

## 4. 2-Week Controlled Sandbox Protocol

Approved candidates undergo a low-risk, time-boxed pilot before any team-wide rollout or paid annual commitment.

### Phase 1: Setup & Data Sanitization (Days 1–2)
* Define **1–2 bounded use cases** and a clear baseline metric (e.g., *hours spent drafting sprint release notes*).
* Restrict pilot access to **2–3 designated team members**.
* Enforce strict **Pre-Prompt Sanitization**: only synthetic, public, or redacted data (`[CLIENT_REDACTED]`, `[INTERNAL_METRIC]`) is permitted during the pilot. No PII, source code secrets, or NDA material.

### Phase 2: Execution & HITL Logging (Days 3–10)
* Pilot users run the tool on real workflow patterns (using sanitized inputs) and log two metrics:
  * **Net Time Saved:** `Time saved generating output` minus `Time spent fact-checking and editing`.
  * **Defect / Hallucination Rate:** Count of factual errors, fabricated citations, biased outputs, or formatting breaks caught during Human-in-the-Loop review.

### Phase 3: Gate Review & Final Decision (Days 11–14)
* Compile a 1-page Pilot Summary comparing net productivity gain against review overhead.
* Issue one of three formal statuses:
  * **ADOPT:** Approve for production, update team onboarding docs, and add approved prompt templates to the *PM Prompt Engineering Library*.
  * **HOLD:** Keep on watchlist pending specific vendor feature or security certification.
  * **REJECT:** Revoke sandbox accounts, purge test data, and document findings.

---

## 5. AI Tool Decision Log (Template)

Maintain a lightweight audit trail so stakeholders never re-evaluate the same tool twice:

| Date | Tool & Version | Target Use Case | Privacy Veto Passed? | Weighted Score | Pilot Net Time Saved | Final Decision | Next Review |
| :--- | :--- | :--- | :---: | :---: | :---: | :---: | :--- |
| `YYYY-MM-DD` | *Example: Gemini for Workspace* | Meeting summaries, Docs drafting, Sheets trackers | Yes (Workspace Enterprise controls) | `4.5 / 5.0` | `~2.5 hrs/week` | **ADOPT** | `Q2 2027` |
| `YYYY-MM-DD` | *Example: Unvetted Free Summarizer* | Client call transcription | **No** (Trains on audio data) | `N/A (Veto)` | `—` | **REJECT** | `N/A` |
