# Pre-Mortem Risk Register & Quality Gate Framework

> **Purpose:** Shift project governance from reactive firefighting to proactive defense. Before execution starts, this template audits historical failure points, quantifies active risks, embeds time/vendor buffers, and enforces mandatory Go/No-Go gates.

---

## 1. Historical Failure Audit (Pre-Mortem Input)

Review past initiatives or industry benchmarks to isolate recurring root causes before locking the delivery schedule.

| Historical Bottleneck | Root Cause Analysis | Embedded Defensive Mechanism |
| :--- | :--- | :--- |
| **Vendor Lead-Time Slippage** | Single-source dependency and unverified shipping SLAs | `+14-day` procurement buffer + pre-vetted secondary supplier agreement |
| **Infrastructure / Connectivity Failures** | Assumed readiness without empirical site testing | Mandatory pre-launch network heatmapping + redundant failover path |
| **Compressed Onboarding & Resistance** | Last-minute training with no hands-on simulation | Certified *Train-the-Trainer* champions + phased pilot before full scale |
| **Late-Stage Compliance Blockers** | Legal/IP review treated as a post-development formality | Mandatory Sprint 0 regulatory, contract, and IP clearance gate |

---

## 2. Active Risk Matrix

**Scoring Scale:** Likelihood (`1` Rare – `5` Almost Certain) × Impact (`1` Minor – `5` Critical) = **Risk Score (`1–25`)**
- **15–25 (Critical / Red):** Immediate executive escalation & hard launch blocker
- **8–14 (Elevated / Amber):** Active mitigation owner & weekly tracking
- **1–7 (Controlled / Green):** Standard monitoring at sprint boundaries

| ID | Category | Risk Event | L | I | Score | Proactive Mitigation (Prevention) | Contingency Plan (If Triggered) | Owner | Status |
| :--- | :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :--- |
| **R-01** | Supply Chain | Hardware / vendor license delay exceeds schedule buffer | 3 | 5 | **15** | Lock multi-source vendor SLA; order 14 days ahead of critical path | Activate pre-approved backup supplier or stagger pilot cohorts | PM / Ops | `Open` |
| **R-02** | Technical | Production system glitches or checkout/API freezes under peak load | 3 | 4 | **12** | Pre-shift diagnostic checklist + staging stress test before pilot | Immediate rollback to fallback UI + hotfix sprint within 24h | Tech Lead | `Mitigated` |
| **R-03** | Compliance / IP | Third-party IP, data privacy (PII), or vendor contract non-compliance | 2 | 5 | **10** | Mandatory Sprint 0 Legal/IP gate + data sanitization protocol | Freeze affected asset/workflow; remediate prior to public release | PM / Legal | `Controlled` |
| **R-04** | Adoption | Low frontline adoption causing workarounds and data errors | 4 | 3 | **12** | Involve floor champions in pilot UAT; simplify UI & ticket formatting | Deploy 1-on-1 refresher drills + daily friction triage during Week 1 | Ops / PM | `Monitoring` |

---

## 3. Mandatory Go / No-Go Quality Gates

A phase cannot advance until **100% of Red/Critical blockers** are resolved or formally accepted in writing by the Executive Sponsor.

### Gate A — Ready for Procurement & Build
- [ ] Project Charter signed with explicit `In-Scope` and `Out-of-Scope` boundaries
- [ ] Vendor 3-year TCO and uptime SLA compared across at least 2–3 options
- [ ] Regulatory, IP, and data-privacy requirements cleared for target jurisdictions

### Gate B — Ready for Pilot Launch
- [ ] Infrastructure stress test / network survey completed with zero critical dead zones
- [ ] Pre-service staging QA passed on 100% of pilot hardware/software units
- [ ] Frontline staff completed hands-on simulation drills and received quick-reference SOPs

### Gate C — Ready for Full Scale
- [ ] Pilot KPIs meet or exceed baseline targets (e.g., error rate, speed, CSAT)
- [ ] Critical pilot friction points resolved and verified in live operations
- [ ] Post-launch support ownership and runbooks formally transferred to BAU operations

---

## 4. Escalation Protocol

| Trigger Threshold | Escalation Path | Response SLA |
| :--- | :--- | :--- |
| **Schedule Slip > 5 Business Days** | Delivery Lead → Ops Director | Within `24 hours` |
| **Projected Budget Variance > +10%** | Delivery Lead → Executive Steering Committee | Within `48 hours` |
| **Critical Security, PII, or IP Breach** | Delivery Lead → Legal Counsel & Sponsor | **Immediate (`< 2 hours`)** |
