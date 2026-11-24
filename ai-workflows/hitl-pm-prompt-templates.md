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
