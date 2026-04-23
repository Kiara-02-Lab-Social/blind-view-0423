# Why fixing color contrast in Figma is not enough for accessibility

## The short version

Color contrast is one checkbox out of dozens. A website can pass every color contrast check and still be completely unusable for a blind person, a keyboard-only user, or someone using a screen reader.

---

## What Figma can check

- Text contrast ratio (4.5:1 minimum for normal text)
- Non-text contrast (3:1 for icons, borders)
- Color choices in the visual design

This covers roughly 10% of WCAG 2.1 compliance criteria.

---

## What requires code — and cannot be seen in Figma

### 1. ARIA labels and roles

Screen readers announce elements by their programmatic name, not their appearance. A button with an arrow icon must have `aria-label="Next slide"` in the HTML. A modal must have `role="dialog"`. A live chat feed must have `aria-live="polite"`. None of this exists until a developer writes it.

Examples:
- `aria-label`, `aria-labelledby`, `aria-describedby`
- `role="dialog"`, `role="alert"`, `role="navigation"`
- `aria-expanded`, `aria-hidden`, `aria-current`
- Error messages linked to form fields via `aria-errormessage`

### 2. Keyboard navigation

Blind users and motor-impaired users navigate by keyboard alone. Requirements:
- Every interactive element reachable with Tab
- Logical tab order that follows visual/reading order
- Modals trap focus inside themselves while open
- Menus operable with arrow keys
- A "Skip to main content" link at the top of every page
- No keyboard traps (user can always Tab out)
- Visible focus indicator on every focused element

### 3. Semantic HTML structure

Screen readers build a mental map of a page from HTML structure, not visual layout. Requirements:
- Headings in logical order (h1 → h2 → h3, never skipped)
- Lists marked up as `<ul>` or `<ol>`, not styled divs
- Buttons as `<button>`, not `<div onclick>`
- Every form input has an associated `<label>`
- Page has landmark regions: `<main>`, `<nav>`, `<header>`, `<footer>`
- Every image has meaningful `alt` text, or `alt=""` if decorative

### 4. Screen reader QA testing

Automated scanners (axe, Lighthouse) catch only about 30% of real accessibility issues. The rest require:
- Manual testing with NVDA (Windows, free)
- Manual testing with JAWS (Windows, enterprise standard)
- Manual testing with VoiceOver (Mac/iOS, built in)
- Ideally, testing with a blind user

---

## Summary for clients

| Layer | Done in Figma? | Done in code? | Requires QA testing? |
|---|---|---|---|
| Color contrast | Yes | No | Automated tools |
| ARIA labels | No | Yes | Manual |
| Keyboard navigation | No | Yes | Manual |
| Semantic HTML | No | Yes | Manual |
| Screen reader testing | No | No | Human tester |

Approving a Figma file for accessibility means approving the color palette. The actual accessibility work has not started yet.
