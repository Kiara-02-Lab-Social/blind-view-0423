# Accessibility Compliance Scope Agreement

Read and sign before design approval

---

## Purpose

This document establishes a shared understanding of what web accessibility compliance requires. Its purpose is to prevent a common and costly misunderstanding: that approving a visual design is equivalent to approving an accessible website.

It is not. This agreement clarifies what each party is responsible for at each stage of the project.

---

## What design approval covers

When the client approves a Figma or design file, they are approving:

- Visual color contrast ratios (text and non-text elements)
- Color palette and visual styling choices
- Layout, spacing, and visual hierarchy
- Annotations specifying intended accessible names for interactive elements

**Design approval does not constitute accessibility compliance. Accessibility compliance requires additional implementation and testing work described below.**

---

## What accessibility compliance actually requires

Full WCAG 2.1 AA compliance is achieved across four distinct stages. Each stage is a separate deliverable.

| Stage | Who is responsible | Deliverable | Client approval required? |
|---|---|---|---|
| 1. Design | Designer | Contrast ratios, focus states, component annotations | Yes — design sign-off |
| 2. Implementation | Developer | ARIA labels, semantic HTML, keyboard navigation | Yes — code review or UAT |
| 3. QA | QA tester | Screen reader audit report (JAWS, NVDA, VoiceOver) | Yes — audit sign-off |
| 4. Launch gate | Project lead | All three stages verified before go-live | Yes — final go/no-go |

---

## What is not included unless explicitly scoped

The following are out of scope unless a separate line item has been agreed and priced:

- PDF accessibility (separate WCAG standard)
- Video captions and audio descriptions
- Third-party embedded widgets (maps, chat tools, payment forms)
- Legacy pages not included in the project scope
- Ongoing monitoring after launch

---

## Definition of done

The website is considered accessible when all of the following are true:

1. Automated scan (axe or Lighthouse) shows zero WCAG 2.1 AA violations
2. Manual keyboard navigation test passes (all interactive elements reachable and operable)
3. Screen reader audit passes on JAWS + Chrome, NVDA + Chrome, and VoiceOver + Safari
4. Audit report has been reviewed and signed off by the client

---

## Acknowledgement

By signing below, both parties confirm they have read and understood this agreement.

Client name: ______________________________________     Date: ____________

Client signature: ______________________________________     Date: ____________

Consultant / auditor: ______________________________________     Date: ____________

Project name: ______________________________________     Date: ____________

---

*Questions? Contact your accessibility consultant before signing.*
