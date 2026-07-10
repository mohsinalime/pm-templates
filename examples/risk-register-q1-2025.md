# Risk Register — Android App Automation Rollout
**Project:** QA Automation Framework — Phase 1  
**PM:** Mohsin Ali  
**Sprint:** Q1 2025 (Sprint 3 & 4)  
**Last updated:** 14 March 2025

---

Quick note on how I use this: I update this every Friday before the weekly sync. Anything that moves to "escalated" goes straight into the standup the next Monday. Learned this the hard way after a missed dependency in Sprint 1 cost us 3 days.

---

## Risk Log

| ID | Risk | Category | Likelihood | Impact | Score | Owner | Mitigation | Contingency | Status |
|---|---|---|---|---|---|---|---|---|---|
| R-001 | Appium version conflict with Android 14 devices | Technical | High | High | Critical | Mohsin | Pinned Appium to 2.2.1 in requirements.txt, tested on 3 device configs before rollout | Fallback to manual regression for Android 14 only while fix is patched | Mitigated |
| R-002 | Only one engineer familiar with POM architecture | Resource | Medium | High | High | Mohsin | Ran 2 internal knowledge-sharing sessions in Sprint 3, documented every module with inline comments | Pair any new scenario work with Hamza until he's comfortable solo | Open |
| R-003 | New feature releases breaking existing test flows mid-sprint | Scope | High | Medium | High | Dev Lead (Ahmed) | Weekly sync with dev team every Monday — get feature list before sprint start | Flag broken tests same day, skip in regression run, log as known issue | Open |
| R-004 | CI/CD pipeline integration delayed by DevOps backlog | Schedule | Medium | Medium | Medium | DevOps (Bilal) | Flagged in Sprint 2 retrospective, added to DevOps backlog with priority tag | Run framework manually until pipeline slot opens — estimated 2 sprint delay max | Open |
| R-005 | Test device availability — only 4 physical Android devices shared across 2 teams | Resource | Low | High | Medium | Office Admin | Booked device slots via shared calendar, priority to QA during regression window | Use Android emulators as backup — already tested, 80% coverage acceptable | Mitigated |
| R-006 | Scope creep — stakeholders requesting web automation before mobile phase complete | Scope | Medium | High | High | Mohsin | Scope clearly defined in project charter, shared with PM and product lead in Sprint 2 kickoff | Present phase completion criteria at next demo — web scope goes to Phase 2 backlog | Open |
| R-007 | PyTest report format not matching management's reporting template | Communication | Low | Low | Low | Mohsin | Will add HTML report plugin in Sprint 4 — takes 1 day | Share raw CSV in the meantime, Hira can format manually if needed | Closed |

---

## Risk Score Matrix I Use

|  | Low Impact | Medium Impact | High Impact |
|---|---|---|---|
| **High Likelihood** | Medium | High | Critical |
| **Medium Likelihood** | Low | Medium | High |
| **Low Likelihood** | Low | Low | Medium |

---

## What I'm watching this sprint

R-002 and R-003 are the ones keeping me up. R-002 because if Hamza moves to another project (which keeps coming up in 1:1s with the team lead), we lose 50% of our framework knowledge overnight. R-003 is just the nature of working in a fast-release environment — devs ship fast, and sometimes QA finds out about a UI change when a test fails at 11pm.

R-006 is manageable for now but I expect it to escalate after the Phase 1 demo. Will prepare a clear Phase 2 scope doc before that meeting.

---

## Closed Risks

| ID | Risk | Closed Date | How it was resolved |
|---|---|---|---|
| R-007 | Report format mismatch | 28 Feb 2025 | HTML reporter plugin added, stakeholders happy with output |
| R-008 | Git branch strategy unclear across team | 10 Feb 2025 | Agreed on feature-branch workflow, documented in repo wiki |

---

*Next review: 21 March 2025 — before Sprint 4 planning*
