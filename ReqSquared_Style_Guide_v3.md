# Req² Style Guide

## Brand

**Req²** is a Talent Acquisition analytics framework by Victor Alberts. Pronounced "req squared." Everything lives under this brand.

### Products

- **RequisitionIQ** — Descriptive statistics engine. Z-scores, survival curves, peer group signals, lifecycle measurement. It measures what's happening now. It is not predictive. It is not classification.
- **TAker** — Data ingestion framework. Assembles real datasets from unrelated sources using formula-driven joins. Every value is real. Nothing is synthetic, generated, or fitted.
- **Req²Regression** — Applied statistics coursework. ISLR Chapters 1-7. Regression, subset selection, LASSO, GAM, classification theory. The academic foundation. Proves the methods. Not a product — a credential.
- **AgentAI** — Personal agentic AI workflow tool. Context switching across work using LLMs. The TA-facing demo layer ("ask your ATS a question") is secondary to personal productivity.

### Logo

DM Sans Bold (700) everywhere. No exceptions. The ² is always superscript, never baseline. Compact mark: R². Full name: ReqSquared (one word, camel case).

### Colors

| Name | Hex | When to use |
|------|-----|-------------|
| Brand Blue | #4472C4 | Primary accent, headers, CTAs, links, logo |
| Light Blue | #84B4E0 | Superscript ², gradients, secondary accent |
| Text | #1A1A2E | Headlines, primary body text on light backgrounds |
| Body | #595959 | Descriptions, secondary body text |
| Muted | #999 | Labels, field text, tag text |
| Faint | #BBB | Footer meta, WIP text, hint text |
| Border | #E2E6EE | Card borders, embed dividers |
| Tool Border | #E8E8EC | Tool UI borders, input fields |
| Surface | #F7F8FA | Tool backgrounds, preview areas |
| White | #FFFFFF | Card backgrounds, page backgrounds |
| Dark Section | #4A4A4A | Carrd dark background sections |

### Fonts

| Font | Role |
|------|------|
| DM Serif Text | Editorial page headers on Carrd ("The Requisition.") |
| DM Sans | Body text, sub-headers, logo |
| DM Sans Bold (700) | Product names — Req², RequisitionIQ, AgentAI, TAker |
| JetBrains Mono | Code, data, technical labels, monospace elements |

Never use more than two font families on one page.

### Text Block Variants

**A — White bg, black header.** Default for most sections.
**B — White bg, blue header.** When the header IS the message.
**C — Blue bg, white header.** Hero sections, callouts, dividers.
**D — Dark bg, blue header.** Footers, contrast breaks, closing statements.

Small headers are always Brand Blue, ALL CAPS, letter-spacing 2-3px regardless of variant.

### Voice

- Open every page with a provocation or bold question, never a description.
- RequisitionIQ measures. Never say it predicts or classifies.
- TAker assembles real data. Never use the word "synthetic" near TAker.
- Data is shown visually (table, chart, matrix), not only described in prose.
- Weave statistical notation into sentences naturally — don't isolate formulas from explanation.

---

## Contexts

Three working contexts exist. Each follows the brand above but has its own rules.

### Carrd Pages

Full Carrd pages at reqsquared.com and sub-pages (req2regression.carrd.co, whatstheproduct.carrd.co, etc.).

**Sizing:** Headers 28-36px. Body 16px. Sub-headers 16-18px. Code/labels 12-14px in JetBrains Mono.

**Layout:** Single column, max ~800px centered. Alternate white/blue/dark background sections — never stack two of the same. Each section has one focal point.

**Hero pattern:** Bold serif header (DM Serif Text) → visual hook → tagline with blue emphasis phrase → resolve line in JetBrains Mono grey → CTA divider → content cards.

**The OG tagline:** "At the center of every stalled requisition is a conversation that never happened." The phrase "conversation that never happened" is always Brand Blue.

### Carrd Embeds

HTML blocks pasted into Carrd embed elements. These sit inside Carrd pages and must not interfere with them.

- Self-contained. No `<html>`, `<head>`, `<body>`.
- All CSS scoped to a unique parent ID: `#rq-card-001 .classname { }`.
- Transparent background by default.
- No `rem` units — Carrd's base font size varies and will break your sizing.
- No `@import` in style blocks — Carrd can strip them. Use font-family with system fallback.
- No media queries unless essential — Carrd handles responsive.
- Each embed is independently functional. Duplicating the code block creates an independent instance.
- Increment IDs per embed: `rq-card-001`, `rq-card-002`, etc.

**Card structure:** Blue gradient bar (3px) → Tag (Req² | LABEL) → Title (bold) → Description → Footer (CTA + meta). Live cards are clickable with hover effects. WIP cards are faded (opacity 0.55), grey bar, not clickable, "In Progress" footer.

**CTA divider:** Horizontal rule with centered label text. JetBrains Mono, 9px uppercase, #BBB. Used between sections to bridge content.

### HTML Tools

Standalone HTML files opened locally in a browser. Workbenches for building content.

**Layout:** Two-column — input left, preview right. Draggable vertical divider between panels. Draggable horizontal divider between preview and code output. Topbar with Req² logo + tool name + zoom controls.

**Scaling:** Tools must be usable on 4K screens without manual browser zoom. Detect `window.devicePixelRatio` and scale base font size accordingly. Include manual zoom controls (−, +, Reset) in topbar as fallback. Range 70-200%.

**Sizing:** Smaller than Carrd pages — these are workbenches. Labels 11px, inputs 15px, code 12px. All in the tool font sizing range, not the page sizing range.

**Output:** Tools generate self-contained embed code that follows the Carrd Embed rules above. Generated code has a config block at top with editable values clearly labeled, and a "DO NOT EDIT BELOW" separator.

**Dependencies:** Vanilla HTML + CSS + JS only. No frameworks. No build steps. Only external dependency allowed is Google Fonts CDN.

**LLM portability:** Every tool file starts with an HTML comment block explaining purpose, brand reference, constraints, and edit zones. Any LLM reading the file should be able to understand and modify it without additional context beyond this style guide.

---

*Req² — The science of the requisition.*
