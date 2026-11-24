# Sprint 0 AI Readiness & Compliance Checklist

> **Purpose:** Operationalize safe, auditable Generative AI adoption across Agile delivery teams before Sprint 1 begins. This checklist enforces Human-in-the-Loop (HITL) governance to prevent data leakage, hallucinated scope, and IP or regulatory blind spots without slowing delivery velocity.

---

## 1. Initiative & AI Tooling Control

| Field | Details |
| :--- | :--- |
| **Project / Product Name** | `[Initiative Name]` |
| **Delivery Lead / PM** | `[Name]` |
| **Approved AI Tools** | `[e.g., Gemini Enterprise / Approved LLM Workspace]` |
| **Target Jurisdictions** | `[ ] EU (EU AI Act)` • `[ ] UK` • `[ ] US` • `[ ] UAE` |
| **Governance Gate Status** | `PENDING / CLEARED FOR SPRINT 1 / HOLD — REMEDIATE` |

---

## 2. The 5-Point Sprint 0 AI Readiness Gate

All five checkpoints must be verified prior to integrating LLMs into project artifacts, backlog workflows, or product features.

### 1. Data Hygiene & Confidentiality
- [ ] Confirmed **zero PII** (Personally Identifiable Information), client identifiers, credentials, or confidential contract clauses enter external prompts
- [ ] Established a mandatory pre-prompt redaction rule (replacing real client names, financial figures, and proprietary code with anonymized placeholders)
- [ ] Restricted prompt inputs exclusively to enterprise-approved workspaces with data isolation enabled

### 2. Source-of-Truth Audit (Anti-Hallucination Control)
- [ ] Assigned a named human reviewer to cross-check every AI-drafted KPI, timeline, SLA, and technical dependency against primary source records (Jira, signed Charters, finance ledgers)
- [ ] Prohibited direct copy-paste of unverified AI outputs into executive reports, Project Charters, or PRDs
- [ ] Logged primary data sources alongside AI-assisted summaries for rapid auditability

### 3. IP, Licensing & Vendor Terms
- [ ] Verified vendor data-retention and **zero-training** settings for all approved AI tools
- [ ] Confirmed commercial usage rights for any AI-assisted text, code, or visual assets before external release
- [ ] Checked third-party software and marketplace policies regarding AI-generated deliverables

### 4. Bias & Operational Edge-Case Review
- [ ] Screened AI-assisted workflows, customer-facing copy, and acceptance criteria for operational edge cases, bias, and policy conflicts
- [ ] Defined deterministic fallback procedures if an AI-assisted step fails or produces low-confidence output
- [ ] Validated that high-stakes decisions (budget approvals, legal clauses, Go/No-Go gates) remain strictly human-owned

### 5. Transparency, Disclosure & Ownership
- [ ] Assigned named human sign-off for every AI-augmented artifact published to Notion, Confluence, or client portals
- [ ] Applied clear AI-disclosure and provenance standards where applicable (**EU AI Act** transparency obligations / **C2PA** alignment)
- [ ] Stored prompt templates and governance updates under version control (GitHub / Confluence)

---

## 3. Core Compliance Traps & Hard Stop Rules

| Compliance Trap | Warning Signal | Mandatory Remediation |
| :--- | :--- | :--- |
| **Confidentiality & Data Leakage** | Raw customer exports, HR data, or NDA clauses pasted into consumer LLM chats | Immediate session termination; sanitize inputs via placeholder mapping before re-prompting |
| **Hallucinated Scope & Metrics** | AI-generated KPIs, dates, or technical assumptions lack a linked primary record | Strip unverified claims; reconcile line-by-line against Jira, charters, or historical logs |
| **IP & Regulatory Blind Spots** | Unaudited vendor retention policies or undisclosed AI-generated public assets | Pause release; verify commercial license terms and apply transparency labeling |

---

## 4. Sprint 0 Governance Sign-Off

| Role | Name | Verification Status | Date |
| :--- | :--- | :--- | :--- |
| Delivery Lead / Agile PM | `[Name]` | `[ ] Verified` | `YYYY-MM-DD` |
| Technical / Security Lead | `[Name]` | `[ ] Verified` | `YYYY-MM-DD` |
| Legal / Compliance Advisor | `[Name]` | `[ ] Verified` | `YYYY-MM-DD` |
