# Accessibility Consulting MVP — Session Summary

**Date:** 2026-04-23
**Topic:** Building a blind-friend-operated accessibility consulting toolkit
**Problem statement:** Clients repeatedly believe that fixing color contrast in Figma is sufficient for accessibility compliance, not understanding that ARIA implementation, keyboard navigation, and screen reader QA are equally required.

---

## What we worked through

### 1. Framing the problem

The core misconception: Figma color contrast fixes cover roughly 10% of WCAG 2.1 AA criteria. The other 90% requires code-level implementation and human testing.

The four layers clients miss:
- ARIA labels and roles (code only, invisible in design tools)
- Keyboard and focus navigation (Tab order, focus traps, skip links)
- Semantic HTML structure (heading hierarchy, landmark regions, form labels)
- Screen reader QA testing (JAWS, NVDA, VoiceOver — manual, not automated)

### 2. MECE analysis of solution space

First attempt at categorization (by action type) had overlaps between Process, Tooling, and Testing. Revised to a timeline-based structure that is genuinely mutually exclusive:

| Phase | What happens |
|---|---|
| Before the project starts | Contracts, scope, education, expectation setting |
| During design | Figma annotation standards, ARIA intent specs |
| During development | Semantic HTML, ARIA implementation, CI tooling |
| During QA | Automated scans, manual keyboard and screen reader testing |
| Before launch | Client sign-off, audit report, launch gate authority |

### 3. Prioritization (objective: min time to first value)

1. **Scope document** — Day 1. A Word doc clients sign before design approval. No code, no setup. Addresses the misconception at the source.
2. **Screen reader test script** — Day 2–3. A checklist your friend runs during QA. Written from lived experience as a blind tester.
3. **CI accessibility gate** — Week 2+. axe-core + GitHub Actions. High long-term value but delayed first value due to setup cost.

### 4. Target user decisions

- **Operator:** your friend (fully blind) — must be operable by keyboard and screen reader alone
- **Recipients:** sighted clients — need something visually clean and professional
- **Screen reader combos covered:** JAWS + Chrome, NVDA + Chrome, VoiceOver + Safari (top 3 by WebAIM survey)

### 5. What was built

**File 1: accessibility-scope-agreement.docx**
A client-facing Word document. One page. Client signs before any design is approved. Contains:
- What design approval does and does not cover
- Four-stage responsibility table (designer → developer → QA → launch gate) — every row has a "yes" owner
- Out-of-scope list (PDFs, video captions, third-party widgets)
- Definition of done (4 criteria)
- Signature lines

**File 2: accessibility-test-script.html**
A self-contained HTML file your friend runs during QA audits. Fully keyboard and screen reader navigable. Contains:
- Project detail fields (name, tester, date, URL)
- 20 test steps across 6 sections
- Per-step: what to do, expected announcement for each of the 3 screen reader combos, WCAG criterion
- Pass / Fail buttons with notes field
- Live progress counter (announced via aria-live)
- Plain text report generator with copy to clipboard
- No server required — opens directly in a browser

---

## Key decisions and rationale

| Decision | Rationale |
|---|---|
| Plain text output default | Tool must be fully usable by a blind operator |
| No visual widgets or diagrams | Ironic but critical — an inaccessible accessibility tool is a credibility failure |
| HTML over native app | No install, no platform dependency, works on any OS with a browser |
| Three SR combos not one | JAWS (enterprise), NVDA (free/common), VoiceOver (Apple) cover the realistic user base |
| Scope doc before test script | Min time to first value — doc ships in a day and works in the next client conversation |

---

## Files produced

| File | Format | Purpose |
|---|---|---|
| `accessibility-scope-agreement.docx` | Word | Client signs before design approval |
| `accessibility-test-script.html` | HTML | Tester runs during QA, generates report |
