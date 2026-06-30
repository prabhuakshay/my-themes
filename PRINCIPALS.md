# UI/UX Instruction Set for a Building Agent

An operating instruction set for an AI agent that designs and builds interfaces. Follow these rules to produce UI that is **good, polished, and professional** — not templated. Covers design principles, visual craft, interaction, accessibility, content, build process, and the anti-patterns to avoid.

> **Scope note:** This set assumes the agent works from a brief and its own judgment, without access to live user research, interviews, or usability sessions. Wherever a principle would normally rely on watching real people, it has been reframed into checks the agent can perform itself — applying heuristics, reasoning from the brief, inspecting its own output (including screenshots), and verifying programmatically. Treat the brief, established heuristics, and self-critique as the substitutes for human testing.

---

## Table of Contents

1. [Foundational Philosophy](#1-foundational-philosophy)
2. [UX Principles & Usability Heuristics](#2-ux-principles--usability-heuristics)
3. [Information Architecture](#3-information-architecture)
4. [Layout & Spacing](#4-layout--spacing)
5. [Typography](#5-typography)
6. [Color](#6-color)
7. [Visual Hierarchy & Polish](#7-visual-hierarchy--polish)
8. [Components & Patterns](#8-components--patterns)
9. [Interaction & Microinteractions](#9-interaction--microinteractions)
10. [Motion & Animation](#10-motion--animation)
11. [Forms & Input](#11-forms--input)
12. [Content & UX Writing](#12-content--ux-writing)
13. [States: Loading, Empty, Error, Success](#13-states-loading-empty-error-success)
14. [Accessibility (a11y)](#14-accessibility-a11y)
15. [Responsive & Adaptive Design](#15-responsive--adaptive-design)
16. [Performance & Perceived Speed](#16-performance--perceived-speed)
17. [Design Systems & Consistency](#17-design-systems--consistency)
18. [Process & Workflow](#18-process--workflow)
19. [Anti-Patterns to Avoid](#19-anti-patterns-to-avoid)
20. [Pre-Ship Checklist](#20-pre-ship-checklist)

---

## 1. Foundational Philosophy

- **Clarity beats cleverness.** If a user has to think about how the interface works, the interface failed — not the user. Specific is always better than clever.
- **Every element earns its place.** Decoration that doesn't serve comprehension or usability is noise. Borrow Coco Chanel's rule: before shipping, remove one thing.
- **Make deliberate, opinionated choices.** Templated defaults are safe and forgettable. A distinctive product comes from choices specific to *this* subject, audience, and job — not the look you'd produce for anything.
- **Constraints create quality.** A small, consistent set of colors, type sizes, and spacing values almost always looks more professional than infinite freedom.
- **Spend boldness in one place.** Pick one signature element to be memorable; keep everything around it quiet and disciplined. Maximalism needs elaborate execution; minimalism needs precision.
- **Design for the real content,** not lorem ipsum. Fake content hides real problems (long names, empty lists, huge numbers, missing images).
- **The quality floor is invisible but mandatory:** responsive to mobile, visible keyboard focus, reduced-motion respected, readable contrast.

---

## 2. UX Principles & Usability Heuristics

Jakob Nielsen's 10 heuristics remain the backbone of usable interfaces:

1. **Visibility of system status** — always show what's happening (loading, saving, progress).
2. **Match between system and the real world** — use the user's language and mental models, not internal jargon. People manage "notifications," not "webhook config."
3. **User control and freedom** — provide undo, cancel, back, and clear exits. Never trap people.
4. **Consistency and standards** — follow platform conventions; the same word/action means the same thing everywhere.
5. **Error prevention** — disable invalid actions, confirm destructive ones, design so mistakes are hard to make.
6. **Recognition over recall** — show options rather than forcing memory. Keep needed info visible.
7. **Flexibility and efficiency** — shortcuts and accelerators for experts, sensible defaults for novices.
8. **Aesthetic and minimalist design** — every extra unit of information competes with the relevant ones.
9. **Help users recognize, diagnose, and recover from errors** — plain language, the cause, and the fix.
10. **Help and documentation** — ideally unneeded, but available, searchable, and task-focused.

**Other durable laws:**

- **Hick's Law** — more choices = slower decisions. Reduce and group options.
- **Fitts's Law** — targets that are bigger and closer are faster to hit. Make primary actions large; put related controls near each other.
- **Miller's Law** — people hold ~7 (±2) items in working memory. Chunk content.
- **Jakob's Law** — users spend most time on *other* sites, so they expect yours to work like those. Don't reinvent standard patterns without reason.
- **Doherty Threshold** — keep system response under ~400ms to keep users engaged and feeling productive.
- **Peak-End Rule** — people judge an experience by its most intense moment and its end. Polish those.
- **Law of Proximity** — things placed close together are perceived as related.

---

## 3. Information Architecture

- **Structure mirrors the user's task,** not your org chart or database schema.
- **Prioritize ruthlessly.** Each screen has one primary job; secondary actions stay visually subordinate.
- **Progressive disclosure** — reveal complexity only when needed. Show the 80% case; tuck the advanced 20% behind "More," accordions, or settings.
- **Group and label by meaning.** Use the end user's vocabulary for navigation labels. Choose terms a non-technical person in the target audience would recognize; avoid system/internal jargon. Sanity-check labels by reasoning through the user's mental model and the established conventions of similar products.
- **Keep navigation shallow and predictable.** Users should always know where they are, where they can go, and how to get back. Breadcrumbs, active states, and consistent placement help.
- **Don't bury frequent tasks.** Frequency of use should drive prominence.

---

## 4. Layout & Spacing

- **Use a spacing scale,** not arbitrary pixel values. A common base is a 4px or 8px system: `4, 8, 12, 16, 24, 32, 48, 64...`. Consistent rhythm reads as professional instantly.
- **Whitespace is a feature.** Generous, intentional space improves comprehension, focus, and perceived quality. Cramped UIs feel cheap.
- **Establish a grid** (e.g., 12-column) and align to it. Alignment is one of the cheapest, highest-impact polish moves — nothing should sit "almost" aligned.
- **Respect proximity.** Related items close, unrelated items apart. Spacing communicates grouping more clearly than borders.
- **Constrain line and content width.** ~50–75 characters per line for body text keeps reading comfortable. Full-width text on large screens is tiring.
- **Consistent padding inside containers.** Cards, modals, and sections should share padding rules.
- **Optical alignment over mathematical.** Sometimes pixel-perfect math looks slightly off (icons, glyphs); trust your eye and nudge.

---

## 5. Typography

Typography carries most of an interface's personality and most of its readability.

- **Pair faces deliberately.** Typically one characterful display/heading face used with restraint, plus a highly legible body face. Avoid pairing two faces that fight; avoid defaulting to whatever you'd use on any project.
- **Set a clear type scale.** Limit yourself to ~5–7 sizes (e.g., `12, 14, 16, 20, 24, 32, 48`) with deliberate weights. A modular scale (1.2–1.333 ratio) gives harmonious steps.
- **Body text ≥ 16px** on the web for comfortable reading. Smaller for captions/labels only.
- **Line-height (leading):** ~1.4–1.6 for body, tighter (~1.1–1.25) for large headings.
- **Letter-spacing:** slightly tighten large headings; slightly loosen all-caps labels and small text.
- **Limit weights** to a few intentional ones (e.g., 400/500/700). Use weight and size for hierarchy before reaching for color.
- **Left-align long text.** Avoid justified text on the web (uneven rivers) and avoid centering anything longer than ~2 lines.
- **Use real punctuation:** curly quotes ("), em dashes (—), proper ellipses (…), non-breaking spaces where needed.
- **Hierarchy through type:** size, weight, color, and spacing should make scanning effortless — a user should grasp the structure without reading.

---

## 6. Color

- **Build a restrained palette:** typically a neutral range (background + several grays for text/borders), one brand/primary color, and a small set of semantic colors (success, warning, error, info). 4–6 core named values go a long way.
- **Use a tonal scale** for each color (e.g., 50→900). Don't hand-pick random shades per use.
- **60-30-10 rule** as a starting balance: 60% dominant/neutral, 30% secondary, 10% accent.
- **Meet contrast standards** (see Accessibility): body text needs **4.5:1**, large text **3:1**. Never rely on color alone to convey meaning — pair with text, icons, or shape.
- **Semantic consistency:** red = destructive/error, green = success, etc. Don't use your error red as a decorative accent.
- **Limit pure black and pure white** for large areas; slightly softened darks/lights (e.g., `#111` / `#FAFAFA`) often feel more refined and reduce eye strain.
- **Test in dark mode and light mode** if you support both — don't just invert; design intentional dark tokens.
- **Watch saturated colors on large fills** — they vibrate and tire the eye; reserve high saturation for small accents.

---

## 7. Visual Hierarchy & Polish

The difference between "fine" and "polished" usually lives in these details:

- **One clear focal point per screen.** The eye should know where to land first.
- **Size, weight, color, and spacing** establish hierarchy. Use the minimum contrast needed to make the order obvious.
- **Consistent corner radii, border weights, and shadows.** Pick a small set and reuse them. Mismatched radii/shadows scream amateur.
- **Shadows that imply real light.** Use soft, layered, low-opacity shadows from a consistent light source rather than harsh single drop shadows. Subtlety reads as expensive.
- **Borders vs. shadows vs. background:** pick one primary method to separate surfaces and apply it consistently.
- **Align everything.** Then check again. Then check the things you thought were aligned.
- **Pixel-snap and avoid blur** on borders, icons, and 1px lines.
- **Icon consistency:** one icon set, one stroke weight, one optical size. Don't mix filled and outlined randomly.
- **Density appropriate to context:** dashboards can be dense; marketing and onboarding should breathe.

---

## 8. Components & Patterns

- **Reuse, don't reinvent.** Use familiar patterns (tabs, modals, dropdowns) so users transfer existing knowledge.
- **Every interactive element needs all its states:** default, hover, focus, active, disabled, loading, selected, and error where relevant. Designing only the default state is the most common polish failure.
- **Buttons communicate priority through hierarchy:** one primary (filled), secondary (outline/tonal), tertiary (text/ghost) per context. Avoid multiple competing primary buttons.
- **Touch targets ≥ 44×44px** (iOS) / **48×48dp** (Android) minimum.
- **Modals sparingly.** They interrupt; use for focused, blocking tasks or confirmations, not as a dumping ground.
- **Tables:** right-align numbers, left-align text, use consistent column padding, support sorting/empty states, and keep headers sticky for long tables.
- **Cards** should have consistent internal structure and not become catch-all containers.
- **Disabled states must explain themselves** or be avoided — a dead button with no reason frustrates users. Prefer enabling + inline validation.

---

## 9. Interaction & Microinteractions

- **Immediate feedback for every action.** A tap, click, toggle, or submit should produce visible, instant acknowledgment (state change, ripple, spinner, toast).
- **Hover and focus states** on every interactive element. Focus must be clearly visible for keyboard users.
- **Optimistic UI** where safe: update the interface immediately and reconcile with the server in the background, with graceful rollback on failure.
- **Confirm only destructive or irreversible actions.** Over-confirming trains users to click through blindly.
- **Prefer undo over confirm** for reversible actions ("Deleted. Undo").
- **Keep the user oriented during transitions** — animate state changes so things don't teleport.
- **Microinteractions should be quick** (often 150–250ms) and have a clear trigger, feedback, and end state.

---

## 10. Motion & Animation

- **Motion serves meaning,** not decoration: it directs attention, shows relationships, explains transitions, and provides feedback.
- **Fast and subtle:** UI transitions usually **150–300ms**. Too slow feels sluggish; too fast feels jarring.
- **Use natural easing.** `ease-out` for elements entering, `ease-in` for leaving, `ease-in-out` for moves. Avoid linear for UI motion.
- **Animate transform and opacity** (GPU-friendly) rather than layout properties like width/height/top for smoothness.
- **One orchestrated moment beats scattered effects.** A coherent page-load or reveal lands harder than many small animations everywhere — and too much motion is a tell-tale sign of generated, unconsidered design.
- **Respect `prefers-reduced-motion`.** Provide a calm, motion-reduced alternative. This is both accessibility and polish.
- **Don't block the user** waiting on animation. Motion should never gate input.

---

## 11. Forms & Input

Forms are where UX is won or lost.

- **Ask for the minimum.** Every field has a cost. Cut, combine, or defer anything you can.
- **Labels always visible** (not placeholder-only — placeholders vanish on input and hurt accessibility). Place labels above fields for fastest scanning.
- **Group related fields** and order them logically (the way a person thinks about the task).
- **Inline, real-time-ish validation:** validate on blur or after the user finishes, show errors next to the field, and explain how to fix — never just "Invalid."
- **Preserve user input** on error. Never clear a form because one field failed.
- **Use the right input types and keyboards** (email, tel, number, date pickers) and appropriate `autocomplete` attributes.
- **Show requirements up front** (password rules, format examples), not only after failure.
- **One column** for most forms; multi-column slows completion and causes errors.
- **Clear primary action,** with the destructive/secondary action visually distinct and harder to hit by accident.
- **Smart defaults** reduce effort — pre-fill what you safely can.
- **Indicate required vs. optional** consistently (marking the rarer one is cleaner).

---

## 12. Content & UX Writing

Words are design material, not decoration — they exist to make the product easier to understand and use.

- **Write from the user's side of the screen.** Name things by what people control and recognize, never by how the system is built.
- **Active voice and concrete verbs.** A control says exactly what it does: "Save changes," not "Submit."
- **Consistent vocabulary throughout a flow.** The button that says "Publish" produces a toast that says "Published." Consistency is how people learn the product.
- **Sentence case** for most UI text (more readable and friendly than Title Case or ALL CAPS).
- **Be specific, not clever.** Specificity builds trust; cleverness creates friction.
- **No filler.** Cut "please," "simply," "just," and apologies. Each element does exactly one job — a label labels, an example demonstrates.
- **Errors don't apologize and are never vague:** state what happened and how to fix it, in the interface's voice.
- **Empty states are invitations to act,** not dead ends.
- **Tone matched to brand and audience,** but always clear first.

---

## 13. States: Loading, Empty, Error, Success

Design these explicitly — they're not edge cases, they're the experience.

- **Loading:** prefer skeleton screens over spinners for content-heavy views (they reduce perceived wait). Show progress for long operations. Keep layout stable to avoid shifts.
- **Empty states:** explain what goes here, why it's empty, and give a clear first action. The first-run empty state is a key onboarding moment.
- **Error states:** plain-language cause + recovery path + a way forward. Keep the user's context and data intact.
- **Partial/zero results:** distinguish "no results for this filter" from "nothing here yet," and offer ways to broaden or reset.
- **Success:** confirm completion clearly (toast, inline confirmation, state change). Don't leave users wondering if it worked.
- **Offline / connection-lost:** detect and communicate; queue or preserve actions where possible.

---

## 14. Accessibility (a11y)

Accessible design is better design for everyone — and often a legal requirement (WCAG 2.1/2.2 AA is the common target).

- **Contrast:** **4.5:1** for normal text, **3:1** for large text (≥24px or ≥19px bold) and meaningful UI components/icons.
- **Don't convey meaning by color alone.** Add text, icons, patterns, or shape.
- **Full keyboard operability:** every action reachable and usable via keyboard, in a logical tab order, with **visible focus indicators**.
- **Semantic HTML / proper roles:** use real buttons, links, headings, lists, and landmarks. Native elements come with accessibility for free.
- **Labels for everything:** form fields, icon-only buttons (`aria-label`), and images (`alt` text; empty `alt=""` for decorative).
- **Respect user settings:** `prefers-reduced-motion`, `prefers-color-scheme`, OS text scaling, and zoom up to 200% without breaking layout.
- **Touch targets ≥ 44–48px** and not too close together.
- **Announce dynamic changes** (toasts, validation, async updates) via live regions so screen readers catch them.
- **Don't disable zoom** or trap focus (except intentionally within modals, which must return focus on close).
- **Verify, don't assume.** Run automated checks (contrast ratios, semantic structure, label presence, tab order), then reason through the keyboard path and screen-reader output manually in code. Automated checks catch only ~30–40% of issues, so trace each interactive flow yourself: confirm every action is reachable by keyboard, focus is visible and ordered logically, and dynamic changes are announced.

---

## 15. Responsive & Adaptive Design

- **Design mobile-first.** Constraints force prioritization; scaling up is easier than cramming down.
- **Fluid, not just fixed breakpoints.** Use relative units (`rem`, `%`, `vw`), flexible grids, `clamp()`, and container queries so layouts breathe between breakpoints.
- **Reflow, don't shrink.** Reorganize content for the viewport rather than scaling a desktop layout to a phone.
- **Thumb-friendly mobile layout:** primary actions within easy reach; avoid critical controls in hard-to-reach corners.
- **Verify across viewports and orientations,** including small phones, tablets, and large desktop monitors (don't let content stretch into unreadable wide lines). Check layouts at common breakpoints and in the gaps between them by inspecting rendered output at multiple widths.
- **Responsive type and spacing,** not just layout — scale sizes sensibly across viewports.
- **Account for notches, safe areas, on-screen keyboards,** and dynamic browser chrome.
- **Images:** serve appropriately sized, modern formats (`srcset`, `WebP/AVIF`), with intrinsic dimensions to prevent layout shift.

---

## 16. Performance & Perceived Speed

Performance *is* UX. A beautiful slow interface feels broken.

- **Aim for the Core Web Vitals:** LCP < 2.5s, INP < 200ms, CLS < 0.1.
- **Eliminate layout shift (CLS):** reserve space for images, ads, and async content.
- **Keep response under the Doherty Threshold (~400ms);** beyond that, show feedback.
- **Perceived performance matters as much as actual:** skeletons, optimistic UI, instant feedback, and progressive rendering make things *feel* fast.
- **Lazy-load** offscreen images and noncritical components; prioritize above-the-fold content.
- **Optimize assets:** compress images, subset fonts, defer noncritical JS/CSS, and avoid render-blocking resources.
- **Don't ship megabytes of JS** for simple interactions. Match technical complexity to actual need.
- **Smooth at 60fps:** animate transform/opacity, avoid jank from heavy work on the main thread.

---

## 17. Design Systems & Consistency

- **Tokenize everything:** colors, spacing, type, radii, shadows, z-index, motion durations. Reference tokens, never magic numbers.
- **Build reusable components** with documented variants and states. Define once, reuse everywhere.
- **Consistency across the product** beats local cleverness. Same patterns, same words, same behaviors.
- **Document usage,** not just appearance: when to use a pattern, when not to, and the content rules around it.
- **Single source of truth** shared by design and engineering to prevent drift.
- **Govern evolution:** add to the system deliberately; prune what's unused. A system is a living product.

---

## 18. Build Process & Workflow

A repeatable path from brief to polished build, executable without human research sessions:

1. **Parse the brief.** Pin the subject, audience, and the page/screen's single job. If any of these are undefined, define them explicitly from context and state the choice you made and why.
2. **Model the user from the brief.** Infer goals, context, likely tasks, and mental models from the stated audience and the conventions of comparable products. Reason about pain points and edge cases instead of inventing user data you don't have.
3. **Define & prioritize.** Map the tasks and flows the interface must support; decide what each screen must accomplish first and what stays subordinate.
4. **Explore widely before converging.** Generate multiple distinct directions internally (sketch structure with ASCII wireframes and flow descriptions). Push past the first/obvious idea before committing.
5. **Plan a token system** — color, type, layout, and one signature element — then **critique it against the brief.** If any part reads like the generic default you'd output for any similar project, revise it and note what changed and why.
6. **Build to the plan.** Derive every color, type, and spacing decision from the tokens. Watch CSS specificity so selectors don't cancel each other out (a common source of broken padding/margins between sections).
7. **Self-critique against this instruction set.** Walk the relevant checklists. Inspect your own rendered output — capture screenshots where the environment allows; rendered output reveals problems that reading code hides.
8. **Verify, don't trust intent.** Programmatically check contrast, semantics, focus order, breakpoints, and layout shift. Trace each interactive flow by keyboard. Confirm every state (loading, empty, error, success, disabled) actually exists.
9. **Apply restraint.** Remove one unnecessary element. Confirm boldness is spent in a single place and everything around it stays quiet.
10. **Iterate against the brief and heuristics,** not guesswork. When a decision is ambiguous, resolve it by appealing to the heuristics in this document and the stated goals — or surface the tradeoff explicitly rather than guessing silently.
11. **Record what you tried.** If you have scratch space, note directions explored and rejected so later passes don't repeat them and can build on prior reasoning.

---

## 19. Anti-Patterns to Avoid

Things that quietly make work look unprofessional or hostile:

- **Templated defaults** applied regardless of subject (e.g., cream background + high-contrast serif + terracotta accent; near-black + single acid-green accent; broadsheet hairline-rule columns). Legitimate for *some* briefs, but a default rather than a choice.
- **Only designing the happy path** — ignoring loading, empty, error, and edge cases.
- **Placeholder-as-label** in forms.
- **Inconsistent spacing, radii, shadows, and icon styles.**
- **Too many fonts, weights, or colors.** Visual noise.
- **Low-contrast "elegant" gray text** that's actually unreadable.
- **Mystery-meat navigation** — icons or labels whose meaning isn't clear.
- **Dark patterns** — tricking, shaming, or pressuring users (forced continuity, confirm-shaming, hidden costs, fake urgency). They destroy trust and increasingly carry legal risk.
- **Motion overload** — everything animating, long animations blocking input.
- **Tiny touch targets** and cramped tap areas on mobile.
- **Centering long text** or full-width unconstrained paragraphs.
- **Removing focus outlines** without replacing them.
- **Disabling buttons silently** with no explanation of what's missing.
- **Reinventing standard controls** (custom dropdowns/checkboxes) that lack keyboard and screen-reader support.
- **Clearing user input on error.**
- **Walls of options** with no defaults or grouping (Hick's Law violations).
- **Inconsistent terminology** for the same action across a flow.

---

## 20. Pre-Ship Checklist

**Visual**
- [ ] Spacing follows a consistent scale; everything aligns to a grid
- [ ] Limited, intentional type scale and color palette
- [ ] Consistent radii, borders, shadows, and icon set
- [ ] One clear focal point per screen; hierarchy is obvious at a glance

**Interaction & States**
- [ ] All interactive elements have hover, focus, active, disabled, and loading states
- [ ] Loading, empty, error, and success states designed (not just happy path)
- [ ] Feedback is immediate for every action
- [ ] Destructive actions confirmed or undoable

**Content**
- [ ] Plain, active, user-centered language; consistent vocabulary across the flow
- [ ] Errors explain cause + fix; empty states invite action
- [ ] Sentence case, no filler, real punctuation

**Forms**
- [ ] Visible labels, helpful inline validation, preserved input on error
- [ ] Minimal fields, smart defaults, correct input types

**Accessibility**
- [ ] Contrast meets 4.5:1 (text) / 3:1 (large text & UI)
- [ ] Fully keyboard operable with visible focus
- [ ] Semantic HTML, labels/alt text, meaning never by color alone
- [ ] `prefers-reduced-motion` and zoom/text-scaling respected
- [ ] Tested with keyboard + screen reader

**Responsive**
- [ ] Works mobile → desktop; reflows rather than shrinks
- [ ] Touch targets ≥ 44–48px
- [ ] No broken layouts at common breakpoints or large screens

**Performance**
- [ ] No layout shift (CLS); images sized and lazy-loaded
- [ ] Fast feedback under ~400ms; perceived speed addressed
- [ ] Assets optimized; no unnecessary JS weight

**Polish**
- [ ] One signature element, everything else quiet
- [ ] Removed one unnecessary thing
- [ ] Inspected rendered output (screenshot) and re-checked against this instruction set

---

*These are operating guidelines, not rigid laws. Break a rule only deliberately, when the brief justifies it and you can state the reason — never by accident or omission.*
