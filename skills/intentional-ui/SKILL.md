---
name: intentional-ui
description: Use when creating, reviewing, or improving frontend UI/UX for websites, landing pages, dashboards, forms, navigation, or game interfaces. Prevents generic AI-generated design (decorative eyebrow labels, purple gradients, emoji icons, tiny low-contrast text, formulaic layouts, vague copy, fabricated proof) and pushes toward product-specific, readable design. Preserves established designs during polish work. Skip backend-only tasks.
---

# Intentional UI

Create interfaces that suit their product and stay comfortable to read and use. Avoid predictable AI-generated aesthetics without swapping in a different cookie-cutter style. **This is a decision-and-verification workflow, not a visual theme.**

## 1. Scope and precedence

Decide which mode applies before changing anything. The mode depends on the task, not just on whether UI already exists. When rules in this skill conflict, this section wins.

- **Existing UI, task is UI improvement** (polish, readability, "make it better," redesign): Preserve the visual identity, layout, interactions, and component system; prefer targeted edits over broad redesigns. Fix readability and usability problems, and remove §4 tells that fail their own test (e.g. an eyebrow that can be deleted without losing information).
- **Existing UI, task is something else** (feature, bug fix): Don't sweep unrelated screens. Follow local conventions in new code and mention notable issues from §4–§5 in your report.
- **New UI:** Apply this skill fully. Derive the direction from the product's content and users, not a default SaaS landing-page formula.
- **What counts as intentional:** Distinctive choices that aren't §4 tells (a custom typeface, an unusual layout, hand-tuned spacing) are preserved by default; they don't need documentation. A §4 tell stays only with evidence — brand guidelines, a documented design-system component, the user saying so, or the pattern carrying real information. Repetition or consistency across the codebase is not evidence; generated codebases repeat their defaults. List every tell you remove in your report so a deliberate one can be restored.
- **Always:** Follow explicit user references and intentional brand conventions. A familiar pattern is not automatically wrong; an unjustified default is.
- **Game interfaces:** Stylized type, uppercase HUD labels, dense displays, and heavy effects can be part of the game's identity. Apply the readability rules to instructions, menus, settings, dialog, and anything players must read under time pressure.

## 2. Hard rules (both modes)

- **Never fabricate proof.** No invented metrics, testimonials, customer logos, user counts, ratings, press mentions, "live" indicators, or trust badges. When real content is missing, use clearly marked placeholders such as `[Customer quote — needs real source]` or `[Metric]`, and list them in your final report.
- **Never invent functionality.** No inert controls, fake progress indicators, or UI for features that don't exist.
- **Never ship unreadable essential text.** Instructions, prices, navigation, CTAs, and form labels must meet the readability rules in §5.

## 3. Start with the product

1. Identify the product, audience, primary task, and what the page actually needs to communicate.
2. Inspect existing components, design tokens, typography, copy, and rendered screens when available.
3. Draft the content and information hierarchy before choosing visual treatments.

## 4. Recurring AI-generated design tells

Treat these as **signals to investigate**. In new UI, remove a pattern unless it carries functional, informational, or product-specific value. In existing UI, follow §1.

**Copy and structure**

1. **Decorative eyebrows/kickers:** A small, uppercase, widely tracked line above a heading (e.g. `A PLACE IN THE NEIGHBORHOOD` above `Come for the coffee`). Keep one only when it supplies distinct information the heading lacks — a real date, step number, category, or location — and consider folding that into the heading or body instead. Don't replace a removed eyebrow with a pill or micro-label.
2. **Formulaic hero:** Kicker + gigantic slogan + vague subheading + two pill buttons. The heading should state something real about the product or task.
3. **Copy-paste page structure:** Centered hero, three feature cards, bento grid, oversized metric strip, generic testimonials, CTA footer.
4. **AI-flavored copy:** "Unlock," "supercharge," "revolutionize," "seamless," "next-generation," comma-stacked vague benefits, explanations that repeat the title.
5. **Self-focused copy where it doesn't belong:** "We built…" claims about the maker instead of the visitor's task or product capability. (First-person voice is fine on a personal site or portfolio.)

**Visual**

6. **Default gradients:** Purple/indigo-to-blue gradients, gradient text, and neon-on-near-black used as the "tech" look.
7. **Default typography:** A typeface used because it's the default rather than chosen — Inter or the system font on a page that needs character, or a fashionable high-contrast editorial serif regardless of the product. (Inter or the system font is often the right choice for tools and dashboards.)
8. **Uppercase as decoration:** `text-xs uppercase tracking-widest`, `font-mono text-[11px] uppercase`, or `letter-spacing: .2em` repeated above section titles. Never put long headings or paragraphs in all caps. Proper nouns, acronyms, and terse functional statuses are fine.
9. **Generic iconography:** Emoji as icons; identical line icons in rounded colored squares on every card.
10. **Ambient effects:** Blurred animated blobs, floating glows, glassmorphism, heavy shadows, and `rounded-2xl` on everything, used only to fill space.
11. **Card soup:** Cards nested in cards, or every piece of content boxed regardless of its relationship to its neighbors.
12. **Everything centered:** Centered alignment for long text, forms, and every section by default.
13. **Decorative chrome:** Gradient-outline pills, version-announcement badges, accent-stripe active states with no coherent state system, gratuitous `·` / `•` separators.

A single familiar device can be appropriate; a collage of unrelated defaults is not.

## 5. Typography and readability

**Readability is a first-class requirement.** Don't fix weak hierarchy by enlarging everything. Diagnose typeface, size, weight, contrast, letter spacing, line length, line height, and whitespace together. Use existing tokens and scales where they exist; the numbers below are starting points for new UI, not a mandate to overwrite an established system.

- **Roles:** Define display, section heading, body, secondary/help text, control label, and metadata/caption, with perceptible size steps between them.
- **Body text:** About 16–19 CSS px (`1rem`–`1.1875rem`). Tiny text is not minimalism.
- **Secondary text:** A modest step down from body with clear contrast — not 10–12px plus muted gray plus wide tracking. Reserve very small text for nonessential metadata.
- **Line height and measure:** Roughly 1.45–1.65 for running text, tighter for short headlines. Aim for 45–75 characters per line, ideally around 60–70 for reading passages.
- **Contrast:** WCAG AA — 4.5:1 for normal text, 3:1 for large text — measured against the actual rendered background, including gradients and images. Don't use low opacity or pale gray to look refined.
- **Typeface and weight:** Legible letterforms with enough stroke weight at the rendered size. Don't swap an established project's font without a reason.
- **Case:** For new UI, default to sentence case for headings and labels. In existing UI, keep the established convention (title case is a valid choice).
- **Spacing:** Keep headings visually attached to their content; avoid forced line breaks, ultra-wide text containers, and gaps that disconnect related information.
- **Responsive and zoom:** Use relative units and responsive adjustments. Content and functionality must survive 200% zoom. Don't make a hero compact by clipping or shrinking essential text.

Whitespace is not an excuse for faint, undersized, or uninformative copy.

## 6. Giving new UI a real identity

Removing tells isn't enough; a page with no eyebrows, sentence case, and safe gray text can still be generic. But don't swap one predictable style for another — no visual treatment is good by default. Aim for coherence, clear hierarchy, and fit with the product.

**For new pages or substantial redesigns, state the design direction in one sentence tied to the product before writing code.** For targeted fixes and additions, follow the established direction without redefining it. Examples of a direction: "dense, neutral, data-first, because analysts scan tables all day" or "warm and photographic, because people choose a café by its atmosphere." Then make every choice serve that sentence.

- **Marketing pages and content sites** usually benefit from a distinct identity: type, color, and imagery that could only belong to this product.
- **Tools, dashboards, and forms** usually benefit from restraint: a familiar, highly legible typeface, a quiet palette with color reserved for state and data, and density appropriate to the task.

The examples below illustrate grounding choices in the product; they are not treatments to apply.

- **Type:** Choose for the product's tone and reading conditions (e.g. a sturdy grotesk for a developer tool, a bookish serif for a publisher, Inter for a data-heavy admin panel). Build hierarchy with weight and size together.
- **Color:** Derive the palette from the product's world — its brand, materials, photography, subject, or data — rather than a default accent. Use as many colors as the content needs (a chart with eight series needs eight) and no more.
- **Content as the visual:** Lead with real product screenshots, photos, data, menus, maps, code samples, or examples instead of abstract decoration.
- **Layout:** Let content shape the layout rather than repeating one block pattern for every section. Symmetry, asymmetry, centered, or left-aligned are all valid when they suit the content.
- **Specificity test:** If the product name changed, would the page still fit any generic startup? If yes, the choices aren't grounded yet.

## 7. Workflow

Work in order of user impact:

1. **Function and flow:** The core task, next action, and system states are clear. Preserve actual behavior.
2. **Content:** Concise, product-specific headings, instructions, and CTA labels (§2 applies).
3. **Typography:** Roles, metrics, contrast, measure, and spacing fixed together (§5).
4. **Layout:** Related content grouped, consistent spacing, no pointless empty areas.
5. **Visual identity:** Grounded choices (§6), restrained effects.
6. **Interactions:** Legible focus, hover, active, selected, disabled, loading, success, and error states. Respect `prefers-reduced-motion`.

For existing UI, search likely components for `uppercase`, `tracking-widest`, `text-xs`, low-opacity text, arbitrary tiny font sizes, and repeated eyebrow/pill patterns — then **read their purpose before changing anything**. Rank findings by impact (unreadable copy and unclear actions before decorative annoyances) and change the smallest useful set of components and tokens. Don't add dependencies or redesign unrelated screens.

## 8. Verification

Check the rendered result, not just the CSS. Use whatever the environment offers:

- **Screenshots:** Render the page in a browser (browser automation tools, Playwright, or Puppeteer) at about **375px** and **1440px** wide. When the layout changed, also check about **768px** and any breakpoint the CSS defines — layouts usually break between 768 and 1024px. Use screenshots to judge hierarchy, balance, wrapping, and regressions.
- **Readability:** Don't judge text size from screenshots; they are downscaled when viewed. Read rendered `font-size`, `font-weight`, and `line-height` via `getComputedStyle` and compare them against the type roles in §5. Passing contrast alone doesn't make text comfortable to read.
- **Contrast:** Read computed `color` and `background-color` for text elements and compute WCAG ratios, or use browser DevTools / Lighthouse accessibility audits. Sample gradients and images at the text's position.
- **Text resize:** Enlarge text alone to 200% and confirm nothing is clipped, overlapped, hidden, or unreachable — this catches fixed-height containers. Prefer simulating the user's default font-size setting (browser settings, or in Chromium the experimental DevTools Protocol `Page.setFontSizes`). Injecting `html { font-size: 200% }` is a weaker diagnostic: it overrides a root locked to `px`, so it can pass a page that ignores user settings. If text doesn't scale, find the cause (`px` sizes, viewport-based `clamp()`, `!important` or inline overrides) rather than assuming one.
- **Zoom and reflow:** Page zoom behaves like a narrower viewport. Confirm content works at **320 CSS px** wide without horizontal scrolling (except for content that needs two dimensions, like data tables or maps).
- **Build:** Run existing build/lint checks and a targeted smoke test; skip expensive unrelated suites.

If a check couldn't be run, say exactly which one and why. **Never claim contrast or zoom compliance you didn't measure.**

Before finishing, confirm:

- The main message and primary action are findable at a glance.
- Body copy, help text, buttons, and navigation are comfortable to read at normal size on desktop and mobile.
- Typography, spacing, icons, and states follow one system.
- Intentional branding, working controls, and unrelated screens are intact.
- Any placeholders for missing real content are listed.

Report meaningful changes, removed tells, and flagged-but-unchanged patterns briefly. Don't put design-process commentary into the UI itself.

## References

- [U.S. Web Design System: typography](https://designsystem.digital.gov/components/typography/)
- [GOV.UK Design System: type scale](https://design-system.service.gov.uk/styles/type-scale/)
- [WCAG 2.2](https://www.w3.org/TR/WCAG22/)
- [Anthropic: prompting for frontend aesthetics](https://platform.claude.com/cookbook/coding-prompting-for-frontend-aesthetics)
