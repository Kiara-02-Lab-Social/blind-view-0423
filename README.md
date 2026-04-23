# Accessibility Consulting Toolkit

A minimal toolkit for blind accessibility consultants to manage client expectations and conduct structured screen reader audits.

**Operated entirely by keyboard and screen reader. No mouse required.**

---

## The problem this solves

Clients routinely approve a Figma design and believe the website is now accessible. It is not. Color contrast — the only thing Figma checks — covers roughly 10% of WCAG 2.1 AA compliance. The rest requires code-level implementation and human testing that no design tool can verify.

This toolkit gives a blind accessibility consultant two concrete tools to fix that misunderstanding before it causes rework.

---

## What's in this toolkit

| File | What it is | Who uses it |
|---|---|---|
| `accessibility-scope-agreement.docx` | Agreement clients sign before design approval | Client + consultant |
| `accessibility-test-script.html` | Screen reader audit checklist with report generator | Consultant (tester) |

---

## Quick start

### Step 1 — Send the scope agreement before any design is approved

Open `accessibility-scope-agreement.docx` in Word or Google Docs. Fill in the project name. Send to the client to read and sign.

This document states clearly that design sign-off is not accessibility sign-off, and defines what all four stages of compliance look like.

### Step 2 — Run the test script during QA

Open `accessibility-test-script.html` in your browser. No server needed, no install required.

Fill in the project details at the top, then work through the 20 test steps using your screen reader. Mark each step Pass or Fail. Add notes for any failures.

When done, press "Generate report" to produce a plain text audit report. Copy it and send to the client.

---

## Keyboard operation guide

The test script is fully keyboard navigable.

| Key | Action |
|---|---|
| Tab | Move to next interactive element |
| Shift + Tab | Move to previous element |
| Enter or Space | Activate button, expand test step |
| Escape | Close expanded section (where applicable) |

All state changes (pass, fail, report generated) are announced via `aria-live` region.

---

## Screen reader combos covered

Each test step documents expected behavior for all three combinations:

| Combo | Who uses it |
|---|---|
| JAWS + Chrome (Windows) | Enterprise and government users — most common in corporate clients |
| NVDA + Chrome (Windows) | Free and open source — most common among blind users generally |
| VoiceOver + Safari (macOS / iOS) | Apple device users — most common for mobile testing |

---

## Test script — sections covered

1. Page structure (title, headings, landmarks, skip link)
2. Keyboard navigation (tab order, focus visibility, no traps)
3. Forms (labels, required fields, error announcements)
4. Interactive components (buttons, links, modals, expanded states)
5. Images and media (alt text, video captions)
6. Dynamic content (status messages, AJAX updates)
7. Overall verdict

20 test steps total. Each maps to a specific WCAG 2.1 criterion.

---

## What the scope agreement covers

- What design approval does and does not include
- Four-stage responsibility table: designer → developer → QA tester → launch gate
- Out-of-scope items: PDFs, video captions, third-party widgets, legacy pages
- Definition of done: automated scan + keyboard test + screen reader audit + client sign-off
- Signature lines for client and consultant

---

## What this toolkit does not cover

- Automated CI scanning (axe-core + GitHub Actions — recommended as a next step once this baseline is in place)
- PDF accessibility (separate WCAG standard, separate engagement)
- Mobile native apps (iOS / Android — requires different testing tools)
- Ongoing post-launch monitoring

---

## WCAG standard

All test steps reference WCAG 2.1 Level AA, which is the standard required by most accessibility laws including:
- ADA (United States)
- EN 301 549 (European Union)
- JIS X 8341-3 (Japan)

---

## Requirements

- A modern browser (Chrome, Firefox, Safari, Edge)
- Microsoft Word or Google Docs (for the scope agreement)
- Your preferred screen reader (JAWS, NVDA, or VoiceOver)
- No internet connection required after download

---

## File structure

```
accessibility-consulting-toolkit/
├── README.md                          — this file
├── SESSION-SUMMARY.md                 — full session log and decision rationale
├── accessibility-scope-agreement.docx — client signs before design approval
└── accessibility-test-script.html     — screen reader audit tool
```

---

## Background

Built in a single session focused on min time to first value. The scope agreement ships on day 1 and works in the next client conversation. The test script ships on day 2–3 and works in the next QA cycle. No infrastructure, no dependencies, no maintenance overhead.

The CI accessibility gate (axe-core + GitHub Actions) is the recommended next step after validating these two tools in practice.
