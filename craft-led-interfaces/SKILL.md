---
name: craft-led-interfaces
description: >-
  Make any web UI feel authored by a human craftsperson instead of generated. Load this WHENEVER building or restyling anything with an interface — an app, website, landing page, dashboard, tool, form, component, or single screen — and especially when the user wants it to feel polished, premium, tactile, considered, "high attention to detail," "not generic," "not templated," or "not AI-looking," even if they don't use those exact words. This is the default craft layer for any frontend work: it replaces component-library defaults and the standard LLM look with subject-specific, physics-aware, fully-detailed design. Use it even for small components and even when the user only says "build me a [X]" without mentioning design.
---

# Craft-Led Interfaces

Generated interfaces look generated for one reason: **every element was left at its default.** The default card, the default instant toggle, the default centered hero, the default spinner, the default "No items yet." Each default is individually reasonable and collectively lifeless, because nobody *decided* anything. The result works and disappears — it could belong to any product.

Craft is the opposite practice: treating each element as a decision with a better, subject-specific answer. It is why one designer, placing a navigation menu, refused the default slide-in drawer and asked "what would a *considered* version of this be?" — and made it open like a book off a shelf. The shelf-menu isn't the point. The *refusal of the default* is the point, and it's available on every element of every screen.

This pays off in more than looks. A considered interface is easier to use, and — this is the real reason it matters — it is one a person can stay inside longer. When a task repeats or runs long, the *feel* of the tool decides whether someone comes back to it tomorrow. Craft is not decoration applied at the end; it is what makes software habitable.

You are not styling a generic thing nicely. You are deciding what *this* thing should be.

> This skill is self-contained and framework-agnostic — usable by any agent, in any stack (React, Vue, Svelte, plain HTML/CSS), and pasteable as a system rule. For full marketing sites and landing pages, pair it with `studio-sites` (concept phase + scroll/WebGL architecture); this skill then owns element-level detail. If your environment also has a dedicated visual-identity skill, it complements this; nothing here depends on it.

---

## 1. The tells — what "generated" looks like

Learn these so you can feel yourself reaching for them. The instinct to fix is: *did I choose this, or did it fall out of the library?*

**Web / landing pages**
- Centered hero: oversized heading, one line of subtext, a primary button and a ghost button beside it.
- Three feature cards in a row, each an icon + heading + one sentence.
- A "Trusted by" logo strip; a big stat with a gradient number; a final "Ready to get started?" CTA band.
- Purple/indigo gradient, soft shadows, generic rounded cards on white, decorative stock icons.

**Apps / tools**
- A dashboard, kanban, or CRUD table chosen by reflex when the task isn't actually a board.
- One dense view trying to serve every task at once.
- Instant state with no motion; uniform spacing; uniform-size elements regardless of importance.
- Lazy in-between states: a bare spinner for loading, "No data" for empty, a red toast that just says "Error."

**Everywhere**
- System font stack untouched; one accent color; 16px spacing on everything.
- Copy that sells or describes the system ("Manage your workflow efficiently") instead of naming what the user controls.

If the finished build could be re-skinned onto a different product by swapping the title and logo, it failed. Craft is the residue of choices that only make sense *here*.

---

## 2. The one move — refuse the default

For every element you place, run two questions:

1. **What is the default** behavior and appearance the library/framework gives this element?
2. **What is the version that belongs to *this* subject** — its world, its materials, its pace?

The gap between those is where craft lives. A menu *can* slide in from the side (default) or turn like pages on a shelf (considered, if the product is about books, archives, journaling). A delete *can* vanish instantly (default) or leave a brief, reversible-feeling gap (considered). A number *can* appear (default) or count up as the data lands (considered).

Two devices make this generative rather than vibes:

- **Name a metaphor.** Find one real-world referent from the subject — a shelf, a ledger, a darkroom, a control desk, a card table, a tide — and let mundane interactions express it. The metaphor turns "make it nice" into "make it behave like *that*." Spend it on the parts the user touches most.
- **Force one sentence per interaction.** Before coding an interactive element, write a single line: "When the user [acts], it [behaves like…]." If the sentence just restates the default, you haven't decided yet.

You don't do this to *every* pixel — that's exhausting and noisy. You do it deliberately, and you spend the boldest version in one place (see §4, the signature).

---

## 3. Where craft actually hides

Quality is not spread evenly. It concentrates in a handful of surfaces that generated UIs skip. This is the universal checklist — it applies to a landing page, a settings panel, or a game.

**Motion & physics.** Replace instant jumps with weighted, spring-based motion *where weight aids understanding* — never everywhere. Inserting an item displaces neighbors with deceleration; dragging adds a slight rotational sway with direction and speed; panels and drawers overshoot their target slightly, then settle (`cubic-bezier(0.175, 0.885, 0.32, 1.275)`, or a spring). Animating everything is itself a tell — and always honor `prefers-reduced-motion`.

**Transitions & continuity.** Elements should move *from where they were*, not teleport. When a small thing becomes a big thing (a card opening to a page), animate the shared element between states so the user keeps their place. Page and view changes are an opportunity for one orchestrated moment, not a hard cut.

**The in-between states.** This is where 90% of generated UIs are laziest and where craft is most visible. For every meaningful surface, design:
- *Loading* — progressive reveal or skeletons that match the eventual layout, not a centered spinner.
- *Empty* — an invitation that tells the user what to do first, not "No data."
- *Error* — what went wrong and how to fix it, in the product's voice; errors don't apologize and are never vague.
- *Success / just-acted* — confirm in place; an action keeps its name through the flow (a "Publish" button yields a "Published" toast).
- *Hover, focus, active, disabled* — each is a real state with a considered treatment, including a visible keyboard focus ring.

**Hierarchy & proportion.** Size, weight, and space should encode what matters. Make important things bigger and quieter things smaller; make a 90-second step physically wider than a 5-second one. Uniform size for unequal things is a tell. Structural devices — numbers, dividers, eyebrows, labels — must encode something *true* (a real sequence, a real grouping), never decorate. Don't number things that aren't a sequence.

**Typography.** Pick a real pairing with personality — a characterful display face used with restraint plus a clean body face — not the system stack. Set an intentional scale (sizes, weights, tracking). Type is the single biggest lever on whether a page feels authored; make it a memorable part of the design, not a neutral delivery vehicle.

**Spacing & density.** Use a spacing scale, not a single value. Decide the intended density (airy and editorial vs. dense and instrument-like) and commit to it consistently.

**Color & surface.** Derive the palette from the subject (4–6 named values), with a restrained accent that means something. Surfaces earn their weight; not everything is a floating card. Avoid the indigo-gradient-on-white reflex unless the brief genuinely calls for it.

**Copy.** Words are design material. Name things by what the user controls and recognizes, in plain active voice, in the product's voice. Specific beats clever. Empty states and errors are copy moments, not afterthoughts.

**Input & feedback.** Feedback is immediate and physical; updates feel optimistic (reflect the user's action before the server confirms, then reconcile). Support keyboard paths. Treat accessibility (focus, contrast, reduced motion, responsive down to mobile) as a quality floor you meet without announcing.

**Restraint and the one-accessory rule.** Maximalist directions need elaborate execution; minimal directions need precision in type and spacing. Either way, before you ship, remove one thing — the most authored interfaces are quiet everywhere except where it counts.

---

## 4. Process

Do most of this in your head or notes; only show the user output when you're confident it will land.

1. **Pin the subject.** If the brief doesn't fix what the product is, fix it yourself: name the subject, its audience, and the single job of the screen, and state your choice. Distinctive decisions come from the subject's world, so go find its materials and vernacular.
2. **Choose the cadence (for apps).** If it's a tool, map the layout to the actual workflow's sequence, not a generic template. Identify the primary constraint the user fights and make managing it the most supported thing on screen.
3. **Pick the signature.** Decide the *one* memorable thing this interface will be remembered by — the shelf-menu, an orchestrated load, a hero that is the subject itself rather than a headline-over-gradient. Spend your boldness here; keep everything around it disciplined.
4. **Lay down a token system.** Before building: a 4–6 color palette (named hex), a type pairing with a scale, a spacing scale, and a motion vocabulary (which gestures get weight, which easing). Derive every later decision from these.
5. **Self-critique against the defaults.** Re-run the brief in your head as a generic agent would. Wherever your plan matches what that generic version would produce, change it and note why. Only then write code.
6. **Build, then remove one accessory.** Meet the quality floor (responsive, keyboard, reduced motion). Then cut the least necessary flourish.

When writing CSS, watch selector specificity — type-based and element-based selectors that both set padding/margins often cancel each other out, especially between sections.

---

## 5. Worked example — applying the mindset

One illustration of the practice (a continuous-take video scripting app). Read it as *what "refuse the default" produced in one case*, not a layout to copy.

The maker's constraint was that videos are recorded as one continuous take, so timing has to be right *before* recording. Every default got re-decided in service of that:

- **Layout maps the workflow:** horizontal columns, one per scene, that double as both a timeline and the editor — you edit a scene where you also see where it sits in the whole.
- **The menu/drawer is the signature:** scripts live in a drawer that opens with a slight overshoot, organized by a deliberately tiny tracker (backlog / in progress / done) so writing never becomes project management.
- **Passive intelligence with a lifecycle:** each scene shows *two* duration figures side by side — an estimate from word count and the assigned value — and the estimate matures (word-count guess → real recorded seconds → nudged up via a segmented stepper to leave room for music and breath). The estimate is visible before it's asked for.
- **Weighted physics on the gestures that matter:** inserting a scene drops an icon at the cursor and pushes neighbors aside with weight; reordering sways like moving something real; an active scene lifts with a shadow while neighbors dim, and a compact control cluster (delete · up · down · add) floats beside it. Deletion is instant but *feels* safe.
- **State-adaptive modes:** locking the scenes flips the whole app from a light, dense compose mode into a focused execute mode — the active scene snaps to first position, its narration enlarges for reading at distance, a dark stage theme replaces the workbench.
- **AI that respects the work:** an optional assistant rewrites a section while considering the surrounding scenes and the duration budget — and its output never overwrites; it lands as a *new version* in the same column, so the user compares and rolls back freely.
- **Capture once, reuse downstream:** references attached to each scene act as tonal anchors *and* feed end-of-flow generation (description, alternate titles for A/B testing) so nothing is rebuilt by hand.

None of those are "a tool template." Each is the considered answer to "what should *this* element be, given *this* constraint." That is the whole method; the outputs differ for every brief.

---

## 6. Smell test — before you ship

Each "yes" on the left is a defect, not a preference.

- Could I re-skin this onto a different product by swapping the title? → Not specific enough; go back to §4.1.
- Did I leave any element at its library default without deciding? → Decide it (§2).
- Is the landing view a centered hero + two buttons, or three icon cards? → Find the subject-specific opener.
- Are loading / empty / error / focus states undesigned? → Design them (§3); they're where craft shows most.
- Does anything teleport where weight or a shared-element transition would aid understanding? → Add it.
- Is an app cramming two phases into one cluttered view? → Split into modes.
- Does any AI action overwrite the user's work? → Make it a non-destructive version.
- Are unequal things drawn at equal size, or is spacing a single uniform value? → Make size and space proportional and scaled.
- Is the type the system stack and the color an indigo gradient? → Re-derive both from the subject.
- Does the copy sell or name system internals? → Rewrite to name what the user controls.
- Did I animate everything / is there clutter? → Cut motion to the load-bearing gestures and remove one accessory.

---

## Using this across agents and models

- **As a skill** (Claude Code, Cowork, similar): drop this folder in; it loads on any frontend build request per the description above.
- **As a rule / system prompt** (Cursor, Windsurf, local models, custom agents): paste the body as a project rule or system instruction. It assumes no special tools.
- **For smaller / local models:** the full text may be a lot to hold. If output quality drops, lead with §2 (refuse the default), §3's in-between-states list, and §6 (smell test) — those three carry most of the gain. Ask for a condensed core if you need one.
