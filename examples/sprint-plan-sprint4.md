# Sprint 4 Plan — QA Automation Framework
**Project:** Android Automation Rollout — Phase 1  
**Sprint dates:** 17 March – 28 March 2025  
**Sprint goal:** Get automation running on 3 remaining apps + deliver HTML reports to stakeholders  
**Team capacity:** 28 points (Mohsin 10pts, Hamza 10pts, Sana 8pts — Sana on half capacity, she has client regression work running parallel)  
**Facilitator:** Mohsin Ali

---

## Sprint Goal — in plain English

By March 28 we should be able to run the full regression suite on Apps 3, 4, and 5 without anyone touching it manually. Stakeholders get an auto-generated HTML report they can actually read. That's the win condition.

Everything else is secondary.

---

## Sprint Backlog

| ID | Task | Priority | Points | Assignee | Status | Notes |
|---|---|---|---|---|---|---|
| T-001 | Write automation scripts — App 3 (Kiddo Fun) login + home flows | High | 5 | Hamza | In Progress | Started Day 1, 60% done |
| T-002 | Write automation scripts — App 4 (Quiz Master) onboarding flow | High | 5 | Mohsin | To Do | Blocked until T-001 review done — same base class |
| T-003 | Write automation scripts — App 5 (Color Kids) core gameplay flow | High | 4 | Hamza | To Do | This one's tricky, has canvas elements — flagged as risk |
| T-004 | Integrate pytest-html plugin for report generation | High | 3 | Mohsin | Done | Merged Friday, stakeholders already got a test report |
| T-005 | Set up scheduled run config — nightly at 2am | Medium | 3 | Mohsin | To Do | Needs DevOps sign-off on server access first |
| T-006 | Fix flaky test on App 2 — settings screen timeout issue | Medium | 2 | Sana | In Progress | Intermittent, reproduces maybe 1 in 4 runs |
| T-007 | Update framework README with App 3–5 setup guide | Low | 2 | Sana | To Do | Only if capacity left after T-006 |
| T-008 | Sprint review deck — 3 slides max | Low | 1 | Mohsin | To Do | Keep it simple, leadership wants numbers not screenshots |
| **Total** | | | **25/28** | | | Left 3pts buffer intentionally — T-003 could expand |

---

## Dependencies and blockers going into sprint

**T-005** is waiting on Bilal (DevOps) to give server credentials. I pinged him twice last week. If no response by Wednesday I'm escalating to the team lead — we can't keep delaying the nightly run.

**T-003** — Color Kids has canvas-based animations. Standard Appium locators won't work well. Hamza flagged this in the Sprint 3 retro. We'll try XPath with bounds fallback first, if that fails we'll use image-based assertions which adds a day.

**Sana's capacity** — she's shared with the client regression project this sprint. I've front-loaded her tasks so she can finish by Thursday and have Friday as buffer.

---

## Definition of Done

A task is done when:
- Code is pushed and reviewed (at least one other person checked it)
- Test runs clean 3 times in a row on the physical device
- Documented in the framework README
- No open comments on the PR

T-008 is done when the deck is shared in the group chat before the review meeting, not during it.

---

## Daily standup format

We do this async on Slack at 9:30am. Three questions:
1. What did I finish yesterday
2. What am I working on today
3. Anything blocking me

If something's blocking you, don't wait for standup — ping me directly. We're a small team, no need for ceremony.

---

## Risks this sprint

**T-003 canvas issue** — Medium likelihood, High impact. If standard locators fail we lose 2 days minimum. Hamza to investigate on Day 1 and report back by lunch.

**Bilal DevOps dependency** — If T-005 doesn't unblock by Wednesday, nightly runs move to Sprint 5. Stakeholders already told, not a crisis but annoying.

**Sana capacity** — If client regression runs long she may not get to T-007. That's fine, it's low priority.

---

## Sprint Retrospective — Sprint 3 (for reference)

**What went well:**
- HTML report integration was faster than expected — Mohsin knocked it out in half a day
- Knowledge sharing sessions helped, Hamza is now comfortable with the POM structure

**What didn't:**
- We took on too much in Sprint 3 — 32 points with a team that realistically does 26-28. Padding is back this sprint.
- App 2 flaky test wasn't caught until final day. Need to add a stability check step before marking tests as done.

**Action items carried into Sprint 4:**
- Stability check added to Definition of Done ✅ (done above)
- Buffer capacity built in ✅
- DevOps dependency flagged earlier ✅ (Day 1 of sprint, not Day 8)

---

*Sprint review: 28 March 2025, 3pm — Board Room 2*  
*Next sprint planning: 31 March 2025, 10am*
