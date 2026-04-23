## Solving the "Figma = accessibility" misconception

### 1. Education
- One-pager or checklist clients sign before design handoff
- Analogy: "Figma is the blueprint, not the building inspection"
- Show a passing-contrast site that fails screen reader testing live

### 2. Process
- Accessibility sign-off requires all four stages (design, code, QA, user test)
- Figma file approval explicitly excludes accessibility compliance sign-off
- Add accessibility acceptance criteria to every ticket, not just design tickets

### 3. Contracts
- Scope accessibility as a separate line item from visual design
- Define "accessible" explicitly (WCAG 2.1 AA, tested with NVDA + VoiceOver)
- Include who is responsible for each layer and what done looks like

### 4. Tooling
- Embed axe DevTools or Accessibility Insights into CI — blocks merge if violations found
- Storybook accessibility addon — developers see ARIA issues at component level
- Figma plugins (A11y Annotation Kit) — designers spec ARIA intent before handoff

### 5. Testing
- Hire a blind QA tester, even part-time or per-project
- Automated scan as baseline, manual as gate
- Record screen reader walkthroughs as evidence for clients

### 6. Pricing
- Bundle accessibility audit as a separate SKU clients can't accidentally skip
- Make the cost of skipping it visible ("without this, WCAG compliance is not guaranteed")

Which of these is most relevant to your friend's situation — freelance, agency, or in-house?
