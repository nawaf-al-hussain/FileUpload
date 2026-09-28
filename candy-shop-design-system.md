# Candy Shop — Design System

> The complete design language of **Candy Shop** (`version: alpha` — *"Bubble gum, cherry red, sugar rush"*), written as a portable spec so it can be applied to **any** website.
> Source: supplied alpha spec (colors · typography · rounded · spacing · components + overview/do's-and-don'ts) · **Dark mode: designed here as a first-class citizen** (ink & paper swap, cherry constant) · Companion file to `open-notebook-design-system.md` — same 16-section anatomy, so the two systems can be diffed or swapped.

---

## Table of Contents

1. [Design Philosophy — The Laws](#1-design-philosophy--the-laws)
2. [Token Architecture](#2-token-architecture)
3. [Color System](#3-color-system)
4. [Typography](#4-typography)
5. [Shape — Radius](#5-shape--radius)
6. [Depth — Shadows](#6-depth--shadows)
7. [Motion](#7-motion)
8. [Iconography](#8-iconography)
9. [Dark Mode Architecture](#9-dark-mode-architecture)
10. [Component Specifications](#10-component-specifications)
11. [Layout System](#11-layout-system)
12. [Application Patterns](#12-application-patterns)
13. [Accessibility](#13-accessibility)
14. [Do & Don't](#14-do--dont)
15. [Porting Guide — Apply to Any Website](#15-porting-guide--apply-to-any-website)
16. [Appendix — Complete Copy-Paste CSS](#16-appendix--complete-copy-paste-css)

---

## 1. Design Philosophy — The Laws

The theme is **"Candy Shop"**: *full-volume joy*. A bubblegum-pink field, cherry-red action, deep-plum ink, rounded everything. It is the deliberate opposite of a quiet enterprise system — yet it is still a *system*: one accent, strict geometry, flat surfaces, and enormous amounts of air. The spec's own words set the laws:

> **cherry acts — exactly one action per screen**
> **bubblegum carries the composition — negative space is a feature**
> **no gradients — this system is flat on purpose**
> **round everything — 14 / 24 / 40, nothing sharp**

Unpacked into operational laws:

| # | Law | Practical meaning |
|---|-----|-------------------|
| 1 | **Cherry acts** | Cherry (`#FF2D6E`) is the *only* interaction color — one primary action per screen. Buttons, active states, links, focus, danger. Reserve it; scarcity is what makes it pop. |
| 2 | **Bubblegum carries** | The page foundation is tinted (`#FFE9F2`), not white and not gray. White is reserved for raised cards. The pink field IS the brand's air — never flatten it to a neutral gray. |
| 3 | **Plum is the ink** | All reading text is deep plum (`#3C0D28`) — never black, never gray. Plum also serves as the "inverse fill" (footer, tooltips, contained tabs, highlight cards). |
| 4 | **Mulberry whispers** | Mulberry (`#B2578C`) is the metadata voice: borders, captions, helper text, dividers, progress fills. It never competes with cherry for attention. |
| 5 | **Flat on purpose** | Zero gradients. Zero shadows on anything anchored to the page. Depth comes from surface color shifts + 1px borders. Only floating layers (dialogs, popovers, toasts) may cast the one sanctioned shadow. |
| 6 | **Round everything** | Radii 14 / 24 / 40px + pill. The floor for containers is 14px. Roundness is the identity — as load-bearing as the single-accent rule. |
| 7 | **Ink & paper swap, cherry stays** | Dark mode inverts the neutrals: bubblegum becomes the ink, plum-black becomes the paper. The cherry never moves — a brand constant across themes. |
| 8 | **Type has two voices** | Fraunces (high-contrast serif) speaks headlines — loud, editorial, slightly wicked. Nunito (rounded sans) does everything else. Never the reverse. |

---

## 2. Token Architecture

Three layers — the portability trick. Components consume **Layer 2 only**; raw hex appears nowhere in component code.

```
Layer 1  RAW VALUES       :root / .dark        → hex for palette, paper, ink, lines ("--raw-*" carriers)
Layer 2  SEMANTIC ALIASES :root (defined once) → --ink: var(--raw-ink); re-resolve automatically in dark
Layer 3  TAILWIND BRIDGE  @theme inline        → maps vars to utilities (bg-accent, text-ink, rounded-md…)
```

> **Critical rule:** inside `.dark`, override **only the raw carriers**. Every alias defined with `var()` re-resolves on its own — never re-declare an alias inside the dark block. Theme switching = toggling the `dark` class on `<html>`.

Recommended (not required) stack:

| Layer | Choice | Notes |
|-------|--------|-------|
| Fonts | Google Fonts: **Fraunces** (variable, opsz 9–144, 600/700) + **Nunito** (400/600/700/800) | One `<link>`, `display=swap` |
| CSS engine | Plain custom properties — or Tailwind v4 via the `@theme inline` bridge | Works framework-free, React/Vue/Svelte/plain HTML alike |
| Icons | Lucide (rounded set) | `stroke-width: 2.25` |
| Toasts | sonner (or equivalent), themed by the same variables | |
| Motion | CSS transitions + `prefers-reduced-motion` guard | No JS animation library needed |
| Theme state | `localStorage['candy-theme']` + no-flash inline script (§16) | light / dark / system |

---

## 3. Color System

### 3.1 Core palette (the 6 owned colors)

| Token | Hex | Name | Role |
|-------|-----|------|------|
| `--plum` | `#3C0D28` | Deep plum | Headlines, body ink, inverse fills (footer, tooltip, highlight cards) |
| `--mulberry` | `#B2578C` | Mulberry | Borders, captions, metadata, muted UI, progress, success checks |
| `--cherry` | `#FF2D6E` | Cherry | **THE accent** — one action per screen; links, active states, focus, danger |
| `--bubblegum` | `#FFE9F2` | Bubblegum | Page foundation (light bg) and dark-mode ink |
| `--paper` | `#FFFFFF` | White | Cards, sheets, inputs (light surfaces) |
| `--on-primary` | `#FFFFFF` | — | Text/icons on plum & cherry fills (constant in both themes) |

### 3.2 Semantic tokens (the portable layer)

Components reference these **only**. Light and dark values side by side — the dark column is the designed palette, not an afterthought.

| Token | Light | Dark | Purpose |
|-------|-------|------|---------|
| `--bg` | `#FFE9F2` | `#1E0A16` | Page canvas |
| `--surface` | `#FFFFFF` | `#2E1224` | Cards, sheets, inputs |
| `--surface-raised` | `#FFFFFF` | `#3A1830` | Hover planes, popovers, menus |
| `--ink` | `#3C0D28` | `#FFE9F2` | Primary text |
| `--muted` | `#8A3A63` | `#E3A8CD` | Captions, metadata, helper text (AA-safe) |
| `--line` | `rgba(178,87,140,.30)` | `rgba(178,87,140,.38)` | Hairline borders, dividers |
| `--line-strong` | `#B2578C` | `#B2578C` | Input borders, emphasized strokes |
| `--accent` | `#FF2D6E` | `#FF2D6E` | Primary buttons, active tab, focus, danger |
| `--accent-hover` | `#E61F5F` | `#FF5C8D` | Hover fill (darker in light, lighter in dark) |
| `--accent-ink` | `#D11450` | `#FF5C8D` | Cherry **as text** — the AA-safe variant |
| `--on-accent` | `#FFFFFF` | `#FFFFFF` | Text on cherry fills |
| `--focus-ring` | `#B2578C` | `#FF5C8D` | `:focus-visible` outline |

Two derivations matter and are part of the system, not optional polish:

- **`--muted` light (`#8A3A63`) is mulberry deepened toward plum.** Raw mulberry on bubblegum is only ~3.9:1 — fine for borders and fills, too weak for caption-size text. The deepened value reaches ~6.3:1. Rule: raw mulberry for *borders/fills*, deepened mulberry for *text*.
- **`--accent-ink` exists because cherry fails as small text in both directions** — cherry text on bubblegum is ~3.1:1, and cherry fill with white text is ~3.6:1. The darker cherry `#D11450` (light) / lighter cherry `#FF5C8D` (dark) restores AA for any cherry-colored *text*.

### 3.3 Contrast ledger (WCAG 2.1, approximate)

**Light**

| Pair | Ratio | Grade |
|------|-------|-------|
| ink `#3C0D28` on bg `#FFE9F2` | 14.2:1 | AAA |
| ink on surface `#FFFFFF` | 16.4:1 | AAA |
| muted `#8A3A63` on bg | 6.3:1 | AA |
| muted on surface | 7.3:1 | AA |
| accent `#FF2D6E` on bg (icons / text ≥24px) | 3.1:1 | AA-large only |
| accent-ink `#D11450` on bg | 4.6:1 | AA |
| on-accent `#FFFFFF` on cherry fill | 3.6:1 | AA-large / bold-label only — see §13 |

**Dark**

| Pair | Ratio | Grade |
|------|-------|-------|
| ink `#FFE9F2` on bg `#1E0A16` | 16.4:1 | AAA |
| ink on surface `#2E1224` | 14.8:1 | AAA |
| muted `#E3A8CD` on bg | 9.7:1 | AAA |
| muted on surface `#3A1830` | 8.4:1 | AAA |
| accent `#FF2D6E` on bg | 5.3:1 | AA |
| accent-ink `#FF5C8D` on bg | 6.5:1 | AA |
| on-accent on cherry fill | 3.6:1 | same caveat as light |

### 3.4 Color usage quick rules

- **One cherry per screen:** if two elements both demand `--accent`, demote one to a plum fill (inverse button) or a mulberry outline (secondary button).
- Cherry on bubblegum works for icons and text ≥24px; for small cherry text switch to `--accent-ink`.
- **Success has no green** — this system owns no green. Success = mulberry Check icon + ink text. Danger IS cherry: on a screen whose primary action is destructive, the destructive button *is* the one cherry.
- Never place a cherry fill directly against a cherry text link without neutral between them — adjacency burns the accent's scarcity.
- Dark mode: **no pure black, no pure white text.** The plum/pink duotone keeps the shop warm at night; `#000` reads cold and cheap next to this palette.

---

## 4. Typography

### 4.1 Font families (2 fonts, strict roles)

| Role | Font | Weights | Fallback stack | Rule |
|------|------|---------|----------------|------|
| **Display** (`--font-display`) | Fraunces (variable, opsz 9–144) | 600, 700 | Georgia, "Times New Roman", serif | Display, h1–h3, big numbers, brand name. At display sizes set `font-variation-settings: "opsz" 144` to get the high-contrast serif cut. **Never body text.** |
| **Body / UI** (`--font-body`) | Nunito | 400, 600, 700, 800 | "Segoe UI", "Helvetica Neue", sans-serif | Everything else: paragraphs, controls, captions, labels. Its rounded terminals echo the radius system — the two families agree with each other. |

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,600;9..144,700&family=Nunito:wght@400;600;700;800&display=swap" rel="stylesheet">
```

### 4.2 Type scale

| Token | Font | Size | Weight | Line-height | Tracking | Usage |
|-------|------|------|--------|-------------|----------|-------|
| `display` | Fraunces | 4.5rem / 72px | 700 | 1.05 | **−0.03em** (spec) | Hero statements only. surrounded by lg/xl space |
| `h1` | Fraunces | 2.5rem / 40px | 700 | 1.15 | −0.02em | Page titles |
| `h2` | Fraunces | 1.75rem / 28px | 700 | 1.2 | −0.01em | Section headers *(derived)* |
| `h3` | Fraunces | 1.25rem / 20px | 600 | 1.3 | 0 | Card titles, dialog titles *(derived)* |
| `body-lg` | Nunito | 1.125rem / 18px | 400 | 1.6 | 0 | Lead paragraphs, empty-state lines *(derived)* |
| `body` | Nunito | 1rem / 16px | 400 | **1.6** (spec) | 0 | Default text |
| `caption` | Nunito | 0.875rem / 14px | 600 | 1.45 | 0 | Helper text, metadata *(derived)* |
| `label` | Nunito | **0.72rem / 11.5px** (spec) | 800 | 1.4 | **+0.04em** (spec) | **Always UPPERCASE** — buttons, chips, badges, overlines, eyebrows |

Rules: labels are *never* sentence case; Fraunces never appears below 1.25rem; body never below 1rem except the `caption`/`label` roles; the scale is **identical in dark mode** — only colors change. Responsive: `display` drops to 3rem under 768px, `h1` to 2rem under 640px.

**Spacing between type blocks:** paragraphs separated by `--space-md` (16px); heading groups `margin-top: var(--space-lg)`, `margin-bottom: var(--space-md)`; label-to-content gap `--space-sm`.

---

## 5. Shape — Radius

**Philosophy: round everything. 14px is the floor for containers; a sharp corner is a bug.**

| Token | Value | Applied to |
|-------|-------|-----------|
| `--radius-sm` | **14px** (spec) | Inputs, selects, textareas, badges, tooltips, chips, small popovers, alerts |
| `--radius-md` | **24px** (spec) | **Buttons** (spec), toasts, dropdown menus, tab groups, images |
| `--radius-lg` | **40px** (spec) | **Cards** (spec), dialogs, modal sheets, hero panels |
| `--radius-pill` | 999px | Switches, progress tracks, dots, avatars, radio, badge-as-dot |

Small-control exemption: controls under ~32px (checkbox ≈8px, radio/dots/avatars full-round) sit outside the scale — a 14px radius on a 20px box would render as a circle anyway. Everything else obeys the ladder; when adding a new component, choose the nearest rung, never a value in between.

---

## 6. Depth — Shadows

**The system is flat on purpose. Anything anchored to the page casts nothing — depth = surface shift + 1px border.**

| Token | Light | Dark | Used by |
|-------|-------|------|---------|
| `--shadow-pop` | `0 12px 32px -8px rgba(60,13,40,0.18)` | `0 12px 32px -8px rgba(0,0,0,0.55)` | Popovers, dropdowns, tooltips, toasts |
| `--shadow-overlay` | `0 24px 56px -12px rgba(60,13,40,0.28)` | `0 24px 56px -12px rgba(0,0,0,0.65)` | Dialogs / modal sheets |
| `--glow-accent` | *(none)* | `0 0 24px rgba(255,45,110,0.18)` | **Dark mode only:** cherry elements glow softly instead of lifting |

Rule of thumb: anchored in the page → border only. Floats above the page → `--shadow-pop`. Blocks the page → `--shadow-overlay`. In dark mode, shadows go blacker and borders do more work; the plum-tinted light shadows would read as haze on the dark paper, so they never carry over.

---

## 7. Motion

**Quick and candy — springy on press, never bouncy on layout.**

| Token | Value | Used for |
|-------|-------|----------|
| `--motion-fast` | 150ms | Hovers, color/opacity transitions |
| `--motion-base` | 250ms | Button press release, dialog pop, toast slide, tab underline |
| `--motion-slow` | 400ms | Sheets, mobile nav, hero entrance |
| `--ease-out` | `cubic-bezier(0.22, 1, 0.36, 1)` | Standard entrances |
| `--ease-spring` | `cubic-bezier(0.34, 1.56, 0.64, 1)` | **The candy signature** — slight overshoot on press-release and pops |

Standard motions:

- **Button press:** `scale(0.97)` at 150ms ease-out on `:active`; on release it springs back with `--ease-spring` — the tactile candy squash. This is the most important micro-interaction in the system.
- **Card hover (interactive):** `translateY(-2px)` + border `--line` → `--line-strong`, 150ms. **No shadow appears** — the flat law holds even on hover.
- **Dialog pop:** `scale(0.96) → 1` + fade, 250ms `--ease-spring`; overlay fades 200ms.
- **Toast:** slide-up 16px + fade, 250ms.
- **Active tab underline:** position/width transition, 250ms ease-out.
- **Skeleton:** `opacity 1 → 0.55` pulse, 1.5s ease-in-out infinite.
- **Theme switch:** `background-color / color / border-color` transition 200ms on `body` so the ink-and-paper swap feels like lights dimming, not a flash.
- **Reduced motion:** under `@media (prefers-reduced-motion: reduce)` — all transforms off, opacity-only, durations collapsed to ~0.

---

## 8. Iconography

- Library: **Lucide**, rounded style — `stroke-width: 2.25` (chunkier than the 2 default, matching the candy weight).
- Sizes: **16px** inline/controls · **20px** nav, input affixes · **24px** empty states, feature rows.
- Color: icons inherit `--ink` or `--muted`; **cherry only for active/selected states** (same budget as everything else).
- Icon buttons always carry `aria-label`.
- Canonical set: `Plus` create · `Search` · `Trash2` delete only · `Pencil` edit · `X` dismiss · `Check` success · `ChevronDown` disclosure · `Sun` / `Moon` theme · `ArrowRight` CTA trails.

---

## 9. Dark Mode Architecture

**Strategy: class-based on `<html>`, three-state preference (light / dark / system), zero flash.**

1. **No-flash script** runs before hydration: reads `localStorage['candy-theme']`, applies the `dark` class on `document.documentElement`, falls back to the system preference, swallows errors (full script in §16).
2. **Tailwind v4 variant:** `@custom-variant dark (&:where(.dark, .dark *));`
3. **Only raw carriers are overridden inside `.dark`** — semantic aliases defined once with `var()` re-resolve automatically (see §2). Never duplicate an alias into the dark block.
4. `color-scheme: light` on `:root`, `dark` under `.dark` — native scrollbars, form controls and autofill follow the theme.
5. **The dark palette law — ink & paper swap, cherry stays:**
   - Paper: bubblegum `#FFE9F2` → plum-black `#1E0A16` (derived from the plum ink, **never `#000`**).
   - Ink: plum `#3C0D28` → bubblegum `#FFE9F2`.
   - Cherry `#FF2D6E` is **byte-identical in both themes** — it is the brand. Hover darkens in light (`#E61F5F`), lightens in dark (`#FF5C8D`), because hover must always move *toward the viewer*.
   - Mulberry `#B2578C` keeps border duty unchanged; text duty moves to the lightened `#E3A8CD`.
   - Shadows go blacker; cherry elements gain the soft `--glow-accent` halo.
6. **Toggle UI:** Sun/Moon icon button in the navbar (Sun rotates/scales out, Moon rotates in) — or a pill switch; optional Light/Dark/System dropdown with the active option marked in `--accent-ink`.

---

## 10. Component Specifications

Every spec below consumes semantic tokens only — no raw hex in components. If you use React + shadcn-style primitives, paste these into cva variants; otherwise copy the declarations literally.

### 10.1 Button

| Variant | Fill | Text | Border | Hover | Active |
|---------|------|------|--------|-------|--------|
| **primary** (spec) | `--accent` | `--on-accent` | none | `--accent-hover` | `scale(0.97)` |
| **secondary** | `--surface` | `--ink` | 1.5px `--line-strong` | bg `--surface-raised`, border `--muted` | `scale(0.97)` |
| **ghost** | transparent | `--muted` | none | bg `--surface-raised`, text `--ink` | `scale(0.97)` |
| **inverse** | `--ink` (plum / pink in dark) | `--bg` | none | `opacity: .9` | `scale(0.97)` |

- **Shape & type (from the spec):** `border-radius: var(--radius-md)` · `padding: 12px 20px` · text in the `label` style (Nunito 0.72rem / 800 / uppercase / 0.04em).
- **Sizes:** sm `padding: 8px 14px` · md (spec default) · lg `padding: 16px 28px` + `--radius-lg` for hero CTAs.
- **Focus:** `outline: 2px solid var(--focus-ring); outline-offset: 2px`. **Disabled:** `opacity: .4; pointer-events: none`.
- The one-cherry rule: **one primary button visible per screen or region.** A second candidate becomes `inverse` or `secondary`.

### 10.2 Card (spec component)

- Base (from the spec): `background: var(--surface); color: var(--ink); border-radius: var(--radius-lg); padding: 24px;` plus `border: 1px solid var(--line)`.
- The spec's **24px padding is canonical** — it deliberately sits between md (16) and lg (32); don't "fix" it to the scale.
- Variants: **plain** (base) · **interactive** (cursor pointer; hover: border `--line-strong` + `translateY(-2px)`, never a shadow) · **selected** (border 2px `--accent` — spends the cherry budget) · **inverse** (`--ink` fill, `--bg` text — stat/highlight cards).
- Header slot: `h3` Fraunces title + `caption` metadata line in `--muted`.

### 10.3 Input & Textarea

- `background: var(--surface); border: 1.5px solid var(--line-strong); border-radius: var(--radius-sm); padding: 10px 14px; font: var(--font-body) 1rem; color: var(--ink);`
- Placeholder `--muted`. **Focus:** border `--accent` + `box-shadow: 0 0 0 3px color-mix(in srgb, var(--accent) 22%, transparent)`.
- **Error:** border `--accent`, helper message in `caption` / `--accent-ink` with an icon (cherry doubles as danger; never introduce a second red).
- Textarea: same spec, `min-height: 96px`. Input height ≥44px on touch targets.

### 10.4 Select

Trigger = Input spec + `ChevronDown` 16px `--muted`. Menu: `--surface-raised`, `--radius-sm`, `--shadow-pop`, border `--line`; items `padding: 8px 14px`, hover bg `--surface-raised` in light / `--surface` lift in dark; **selected** item text `--accent-ink` + trailing `Check` 16px.

### 10.5 Checkbox, Radio, Switch

- **Checkbox:** 20px box, 8px radius (small-control exemption); checked = `--accent` fill + white `Check`; unchecked = 1.5px `--line-strong` on `--surface`.
- **Radio:** 20px circle; checked dot `--accent` at 8px.
- **Switch:** 40×22 track, `--radius-pill`; off = `--line-strong` track, on = `--accent` track (with `--glow-accent` in dark); white knob, 250ms `--ease-spring`.

### 10.6 Tabs

- Underline style (signature): `caption` text; inactive `--muted`; active `--accent-ink` + 2px rounded underline in `--accent`; track bottom border 1px `--line`; underline glides (250ms ease-out).
- Contained variant: pill group on `--surface` with 1px `--line`; active pill = `--ink` fill with `--bg` text (no cherry spent).

### 10.7 Badge & Chip

- **Badge:** `label` style, `--radius-pill`, `padding: 3px 10px`. Neutral: bg `--bg`, text `--muted`, 1px `--line` border (dark: bg `--surface-raised`). Accent badge: `--accent` fill / `--on-accent` text — spend only when the badge IS the screen's one action (e.g. "NEW" on the hero card).
- **Chip:** `caption` text, `--radius-pill`, border `--line-strong`, removable `X` 14px, hover bg `--surface-raised`.

### 10.8 Dialog

- Panel: `--surface`, `--radius-lg`, `padding: var(--space-lg)` (32px), max-width 480px, `--shadow-overlay`; pop animation per §7.
- Overlay: `rgba(60,13,40,0.45)` light / `rgba(10,3,8,0.6)` dark; optional `backdrop-filter: blur(2px)`.
- Title `h3` Fraunces; body `body`; actions right-aligned — **at most one primary**. Close `X` 16px `--muted`, top-right.
- Mobile: bottom sheet, radius lg on top corners only, slide-up 400ms.

### 10.9 Popover & Tooltip

- **Popover:** `--surface-raised`, `--radius-sm`, `--shadow-pop`, border `--line`; arrow optional, same fill.
- **Tooltip:** inverse — bg `--ink`, text `--bg`, `--radius-sm`, `caption` 600, `padding: 6px 10px`; fades 150ms. In dark mode this means a pink tooltip with plum text — the swap is the charm.

### 10.10 Alert

Flat and border-led — **no tinted washes** (the flat law):

- Base: `background: var(--surface); border: 1.5px solid var(--line-strong); border-radius: var(--radius-sm); padding: var(--space-md);`
- **Info:** `--line-strong` border, `--ink` text, `Info` icon `--muted`.
- **Success:** `Check` icon + title in `--secondary` (mulberry — there is no green in this universe), body `--ink`.
- **Danger:** `--accent` border, `AlertTriangle` icon + title in `--accent-ink`, body `--ink`.

### 10.11 Toast

- `--surface-raised`, `--radius-md`, `--shadow-pop`, border `--line`, `padding: var(--space-md)`; slide-up 16px + fade entrance, auto-dismiss 5s.
- Title `caption` 700 in `--ink`; description `caption` in `--muted`; status icon per §10.10 semantics.

### 10.12 Progress, Skeleton, Separator

- **Progress:** track 8px `--radius-pill` in `--line`; fill `--secondary` (mulberry — ambient state, not an action, so the cherry budget stays intact; flip to `--accent` only when the progress bar is the screen's hero metric).
- **Skeleton:** bg `--surface-raised`, `--radius-sm`, pulse per §7. Never gray — the pink family only.
- **Separator:** 1px `--line`. Vertical rails use the same value.

### 10.13 Link

- **Inline text links:** `--accent-ink`, `text-decoration: underline`, `text-underline-offset: 3px`, `text-decoration-thickness: 1.5px`; hover → `--accent` (light) / brightens in dark. Links are wayfinding, not actions — they don't consume the one-cherry budget, but keep them sparse.
- **Nav links:** `caption`/`body` 600 in `--muted`, hover `--ink`; active = `--accent-ink` + underline.

### 10.14 Navbar & Footer

- **Navbar:** transparent on `--bg`, height 72px, container per §11; brand in Fraunces 700 1.25rem `--ink`; links per §10.13; theme toggle; CTA = Button primary (**this is where the page's cherry usually lives**). Mobile: full-screen sheet on `--bg`, links at `h1` size, 400ms slide.
- **Footer:** the inverse moment — bg `--ink` (plum in light, pink in dark), text `--bg`, captions in `--muted`; no cherry down here. The flip is the system's signature closing move.

---

## 11. Layout System

| Token | Value | Notes |
|-------|-------|-------|
| `--container` | 1120px | Default content max-width |
| `--prose` | 720px | Long-form reading column |
| Gutter | `--space-md` (16px) | Page side padding |
| Section gap | `--space-lg` (32px); 64px between major sections | Vertical rhythm |
| Card grid gap | `--space-md` (16px) | |

- **Breakpoints:** 640 / 768 / 1024 / 1280.
- **Page anatomy:** `--bg` shows *between* cards — the bubblegum field is the composition (negative space is a feature, per the spec). Cards float on it with radius lg; the pink is never covered edge-to-edge.
- **Grids:** card grids 3-col ≥1024 · 2-col ≥640 · 1-col below. Gap md; interactive cards align to the same baseline row height per row.
- **Hero pattern:** `display` type + `--space-xl` vertical padding + one primary CTA. The hero owns the page's single cherry; everything below it is mulberry/plum.
- **Z-index ladder:** dropdown 1000 · sticky 1100 · overlay 1200 · modal 1300 · toast 1400 · tooltip 1500.

---

## 12. Application Patterns

### 12.1 The one-cherry audit (run before shipping)
List every accent-colored element on the screen. Exactly **one** may be a call to action. Demotions: extra CTAs → `inverse`/`secondary` button; badges → neutral; progress → mulberry; active tab underline & inline links → `--accent-ink` (wayfinding, allowed); focus rings don't count. If the screen feels under-accented, add whitespace — never a second cherry.

### 12.2 Status system (no green exists)

| State | Treatment |
|-------|-----------|
| Pending | `--muted` dot (6px, pill) + `caption` "Queued" |
| Busy | `--muted` dot pulsing + `caption` "Processing…" |
| Done | `--secondary` `Check` 16px + `caption` |
| Failed | `--accent-ink` `X` 16px + `caption`; full-width failures use the Danger alert |

### 12.3 Empty state
Fraunces `h3` line ("Nothing here yet — sweet."), one `body-lg` sentence in `--muted`, one ghost button. No illustration required; **whitespace is the decoration**. Never fill the void with a cherry CTA unless creating is genuinely the page's one action.

### 12.4 Metadata line
`label` style in `--muted`, items joined by "·": `UPDATED 2 DAYS AGO · 6 SOURCES · 3 NOTES`. Sits under card titles and page titles alike.

### 12.5 Loading
Buttons keep their width (`min-width` locked) while the label swaps to a 16px spinner + "WORKING…" in the same label style. Route-level loads use skeletons (§10.12). Spinners never exceed 24px; never a full-screen spinner over the bubblegum field — skeleton the cards instead.

### 12.6 Prose & markdown
Reading column 720px. Paragraphs `body` / 1.6 with 16px gaps; headings Fraunces h1–h3 with `--space-lg` top margin; links per §10.13; blockquote = 2px `--secondary` left border + `--muted` text; inline code = `--surface-raised` bg, `--radius-sm`, 0.875rem; `kbd` = pill, 1px `--line-strong`, 0.72rem. Images inside prose get `--radius-md`.

### 12.7 Theme toggle placement
Navbar right, before the CTA. Icon button 40×40, `--radius-pill`, ghost hover (bg `--surface-raised`). Icon cross-fades Sun↔Moon with a rotate.

---

## 13. Accessibility

- **Focus everywhere:** `:focus-visible { outline: 2px solid var(--focus-ring); outline-offset: 2px; }` on every interactive element. Never `outline: none` without a replacement ring.
- **Contrast:** ledger in §3.3. Every text pair is AA or better **except one known tension**: white text on cherry fills ≈ 3.6:1 — AA only for large/bold text. Sanctioned mitigations, pick one per project and document it:
  1. **Keep the spec** (white + `label` 800) and treat primary buttons as large-scale UI — the spec's own stance; log it as a known exception.
  2. **Swap button text to plum** `var(--plum)`: 4.6:1 on cherry ✓ — and very much on-brand candy.
  3. **Deepen the fill** to `--accent-ink` `#D11450` for text-critical buttons: 5.3:1 ✓.
- **Never color alone:** pair cherry/mulberry states with icons (`Check`, `X`, `AlertTriangle`) and text labels — the single-accent rule makes this non-negotiable, since hue can't encode category here.
- **Targets:** ≥44×44px on touch (buttons go `lg` on mobile; inputs ≥44px tall).
- **Reduced motion:** transforms off, opacity-only (§7).
- **Forms:** errors announced via `aria-describedby`; never color-only. Labels stay visible — placeholder-only inputs are banned.
- **Dark mode:** same ledger, right column — all pairs AA or better, sharing only the cherry-fill caveat above.

---

## 14. Do & Don't

**Do**

- **Do** use Tertiary for exactly one action per screen. *(spec)*
- **Do** let Neutral carry the composition — negative space is a feature. *(spec)*
- Do keep the cherry byte-identical across themes — `#FF2D6E` is the brand, not a theme preference.
- Do swap shadows for borders + surface shifts in dark mode, and give cherry elements the soft `--glow-accent` instead.
- Do round everything — 14/24/40, pill where things are circular by nature; the squash-press (`scale .97` + spring release) is the tactile signature.

**Don't**

- **Don't** introduce gradients. This system is flat on purpose. *(spec)*
- **Don't** mix Tertiary with alternate accents; the single-accent rule is load-bearing. *(spec)*
- Don't reach for pure `#000`/`#0A0A0A` pages in dark mode — plum-black `#1E0A16` keeps the warmth; and no pure-white body text on dark surfaces (bubblegum ink is the voice).
- Don't use gray body text — muted text is always plum-family (`#8A3A63` light / `#E3A8CD` dark), never `#6B7280`-style cool grays.
- Don't place a cherry fill next to cherry text, and don't spend the accent on decoration — the moment cherry is everywhere, it is nowhere.

---

## 15. Porting Guide — Apply to Any Website

1. **Copy the CSS** from §16 into your global stylesheet (works with or without Tailwind — plain custom properties) and add the two font `<link>`s from §4.1.
2. **Map type roles:** Fraunces for display/h1–h3 only; Nunito everywhere else; `label` always uppercase 800 with 0.04em tracking.
3. **Wire the theme switch:** `dark` class on `<html>`, the no-flash inline script, only raw carriers overridden inside `.dark`. Persist to `localStorage['candy-theme']`; default to system.
4. **Tailwind v4:** paste the `@theme inline` bridge — `bg-accent`, `text-ink`, `rounded-md`, `font-display` work instantly. **Tailwind v3:** use the compact config in §16. **Plain CSS / other frameworks:** reference `var(--…)` directly; the few utility classes at the end of §16 cover 90% of pages.
5. **Rebuild components from §10** — every value is a token reference; if you ever type a hex inside a component, you've broken the architecture.
6. **Respect the laws (§1)** — the aesthetic collapses without the discipline. When in doubt: fewer accents, more whitespace, rounder corners, flatter surfaces.
7. **Smoke test:** toggle dark mode (the ink/paper swap must feel like the same shop at night — same cherry, warmer dark), count accent elements per screen (≤1 action), tab through the UI (mulberry/pink rings everywhere), hover every card (border darkens + 2px lift, no shadow), press a button (squash + spring).

---

## 16. Appendix — Complete Copy-Paste CSS

The entire token layer, self-contained and framework-agnostic (Tailwind bridges included separately at the end). Drop into your global stylesheet.

```css
/* ============ CANDY SHOP — tokens ============ */

:root {
  color-scheme: light;

  /* — Layer 1a: brand constants (identical in both themes) — */
  --plum: #3C0D28;
  --mulberry: #B2578C;
  --cherry: #FF2D6E;
  --bubblegum: #FFE9F2;
  --white: #FFFFFF;

  /* — Layer 1b: raw carriers (the ONLY things overridden in .dark) — */
  --raw-bg: #FFE9F2;
  --raw-paper: #FFFFFF;
  --raw-paper-raised: #FFFFFF;
  --raw-ink: #3C0D28;
  --raw-muted: #8A3A63;      /* mulberry deepened for AA text */
  --raw-line-alpha: 0.30;
  --raw-accent-hover: #E61F5F;
  --raw-accent-ink: #D11450; /* cherry deepened for AA text */
  --raw-focus: #B2578C;

  /* — Layer 2: semantic aliases (defined ONCE; re-resolve in dark) — */
  --bg: var(--raw-bg);
  --surface: var(--raw-paper);
  --surface-raised: var(--raw-paper-raised);
  --ink: var(--raw-ink);
  --muted: var(--raw-muted);
  --line: rgba(178, 87, 140, var(--raw-line-alpha));
  --line-strong: var(--mulberry);
  --accent: var(--cherry);
  --accent-hover: var(--raw-accent-hover);
  --accent-ink: var(--raw-accent-ink);
  --on-accent: #FFFFFF;
  --focus-ring: var(--raw-focus);
  --overlay: rgba(60, 13, 40, 0.45);

  /* shape (spec) */
  --radius-sm: 14px;  --radius-md: 24px;  --radius-lg: 40px;  --radius-pill: 999px;

  /* spacing (spec: sm 8 / md 16 / lg 32; xs-xl derived) */
  --space-xs: 4px;  --space-sm: 8px;  --space-md: 16px;
  --space-lg: 32px; --space-xl: 64px; --space-2xl: 128px;

  /* motion */
  --motion-fast: 150ms;  --motion-base: 250ms;  --motion-slow: 400ms;
  --ease-out: cubic-bezier(0.22, 1, 0.36, 1);
  --ease-spring: cubic-bezier(0.34, 1.56, 0.64, 1);

  /* the only sanctioned shadows (floating layers) */
  --shadow-pop: 0 12px 32px -8px rgba(60, 13, 40, 0.18);
  --shadow-overlay: 0 24px 56px -12px rgba(60, 13, 40, 0.28);

  /* layout */
  --container: 1120px;  --prose: 720px;

  /* type */
  --font-display: "Fraunces", Georgia, serif;
  --font-body: "Nunito", "Segoe UI", sans-serif;
}

.dark {
  color-scheme: dark;
  /* ink & paper swap — cherry stays */
  --raw-bg: #1E0A16;
  --raw-paper: #2E1224;
  --raw-paper-raised: #3A1830;
  --raw-ink: #FFE9F2;
  --raw-muted: #E3A8CD;
  --raw-line-alpha: 0.38;
  --raw-accent-hover: #FF5C8D;
  --raw-accent-ink: #FF5C8D;
  --raw-focus: #FF5C8D;
  --overlay: rgba(10, 3, 8, 0.60);
  --shadow-pop: 0 12px 32px -8px rgba(0, 0, 0, 0.55);
  --shadow-overlay: 0 24px 56px -12px rgba(0, 0, 0, 0.65);
  --glow-accent: 0 0 24px rgba(255, 45, 110, 0.18);
}

/* ============ base ============ */
*, *::before, *::after { box-sizing: border-box; }

body {
  margin: 0;
  background: var(--bg);
  color: var(--ink);
  font-family: var(--font-body);
  font-size: 1rem;
  line-height: 1.6;
  transition: background-color 200ms var(--ease-out), color 200ms var(--ease-out),
              border-color 200ms var(--ease-out);
}

h1, h2, h3, .display { font-family: var(--font-display); }
.display { font-size: 4.5rem; font-weight: 700; letter-spacing: -0.03em; line-height: 1.05; font-variation-settings: "opsz" 144; }
h1 { font-size: 2.5rem;  font-weight: 700; letter-spacing: -0.02em; line-height: 1.15; }
h2 { font-size: 1.75rem; font-weight: 700; line-height: 1.2; }
h3 { font-size: 1.25rem; font-weight: 600; line-height: 1.3; }

.label   { font-family: var(--font-body); font-size: 0.72rem; font-weight: 800; letter-spacing: 0.04em; text-transform: uppercase; line-height: 1.4; }
.caption { font-size: 0.875rem; font-weight: 600; line-height: 1.45; color: var(--muted); }

:focus-visible { outline: 2px solid var(--focus-ring); outline-offset: 2px; }

/* ============ component recipes ============ */
.btn {
  display: inline-flex; align-items: center; gap: 8px; border: 0; cursor: pointer;
  border-radius: var(--radius-md); padding: 12px 20px;
  font-family: var(--font-body); font-size: 0.72rem; font-weight: 800;
  letter-spacing: 0.04em; text-transform: uppercase; line-height: 1.4;
  transition: transform var(--motion-fast) var(--ease-out),
              background-color var(--motion-fast) var(--ease-out),
              border-color var(--motion-fast) var(--ease-out),
              color var(--motion-fast) var(--ease-out);
}
.btn:active { transform: scale(0.97); transition-timing-function: var(--ease-spring); }
.btn:disabled { opacity: 0.4; pointer-events: none; }
.btn-primary { background: var(--accent); color: var(--on-accent); }
.btn-primary:hover { background: var(--accent-hover); }
.btn-secondary { background: var(--surface); color: var(--ink); border: 1.5px solid var(--line-strong); }
.btn-secondary:hover { background: var(--surface-raised); border-color: var(--muted); }
.btn-ghost { background: transparent; color: var(--muted); }
.btn-ghost:hover { background: var(--surface-raised); color: var(--ink); }
.btn-inverse { background: var(--ink); color: var(--bg); }
.btn-inverse:hover { opacity: 0.9; }
.btn-sm { padding: 8px 14px; }
.btn-lg { padding: 16px 28px; border-radius: var(--radius-lg); }

.card { background: var(--surface); color: var(--ink); border: 1px solid var(--line); border-radius: var(--radius-lg); padding: 24px; }
.card-interactive { cursor: pointer; transition: transform var(--motion-fast) var(--ease-out), border-color var(--motion-fast) var(--ease-out); }
.card-interactive:hover { border-color: var(--line-strong); transform: translateY(-2px); }
.card-selected { border: 2px solid var(--accent); }
.card-inverse { background: var(--ink); color: var(--bg); border-color: transparent; }

.input {
  width: 100%; background: var(--surface); color: var(--ink);
  border: 1.5px solid var(--line-strong); border-radius: var(--radius-sm);
  padding: 10px 14px; font: 400 1rem/1.6 var(--font-body);
}
.input::placeholder { color: var(--muted); }
.input:focus { outline: none; border-color: var(--accent);
  box-shadow: 0 0 0 3px color-mix(in srgb, var(--accent) 22%, transparent); }

.link { color: var(--accent-ink); text-decoration: underline; text-underline-offset: 3px; text-decoration-thickness: 1.5px; }
.link:hover { color: var(--accent); }

.divider { border: 0; height: 1px; background: var(--line); }
.container { max-width: var(--container); margin-inline: auto; padding-inline: var(--space-md); }

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

```css
/* ============ Tailwind v4 bridge (optional — paste into the same stylesheet) ============ */
@custom-variant dark (&:where(.dark, .dark *));

@theme inline {
  --color-bg: var(--bg);
  --color-surface: var(--surface);
  --color-surface-raised: var(--surface-raised);
  --color-ink: var(--ink);
  --color-muted: var(--muted);
  --color-line: var(--line);
  --color-line-strong: var(--line-strong);
  --color-accent: var(--accent);
  --color-accent-hover: var(--accent-hover);
  --color-accent-ink: var(--accent-ink);
  --color-on-accent: var(--on-accent);
  --color-plum: var(--plum);
  --color-mulberry: var(--mulberry);
  --color-cherry: var(--cherry);
  --color-bubblegum: var(--bubblegum);
  --radius-sm: 14px;  --radius-md: 24px;  --radius-lg: 40px;
  --font-display: "Fraunces", Georgia, serif;
  --font-body: "Nunito", "Segoe UI", sans-serif;
}
/* → utilities unlocked: bg-accent, text-ink, text-muted, border-line-strong,
   rounded-md, rounded-lg, font-display, dark:bg-… */
```

```js
// ============ Tailwind v3 config (alternative) ============
module.exports = {
  darkMode: "class",
  theme: {
    extend: {
      colors: {
        bg: "var(--bg)", surface: "var(--surface)", "surface-raised": "var(--surface-raised)",
        ink: "var(--ink)", muted: "var(--muted)", line: "var(--line)", "line-strong": "var(--line-strong)",
        accent: "var(--accent)", "accent-hover": "var(--accent-hover)", "accent-ink": "var(--accent-ink)",
        "on-accent": "var(--on-accent)",
        plum: "#3C0D28", mulberry: "#B2578C", cherry: "#FF2D6E", bubblegum: "#FFE9F2",
      },
      borderRadius: { sm: "14px", md: "24px", lg: "40px", pill: "999px" },
      fontFamily: { display: ["Fraunces", "Georgia", "serif"], body: ["Nunito", "Segoe UI", "sans-serif"] },
      boxShadow: { pop: "var(--shadow-pop)", overlay: "var(--shadow-overlay)" },
      transitionTimingFunction: { out: "cubic-bezier(0.22,1,0.36,1)", spring: "cubic-bezier(0.34,1.56,0.64,1)" },
    },
  },
};
```

```html
<!-- ============ no-flash script (in <head>, before first paint) ============ -->
<script>
  (function () {
    try {
      var t = localStorage.getItem("candy-theme");
      var dark = t ? t === "dark" : window.matchMedia("(prefers-color-scheme: dark)").matches;
      document.documentElement.classList.toggle("dark", dark);
    } catch (e) {}
  })();
</script>
```

```js
// ============ toggle wiring ============
function applyTheme(dark) {
  document.documentElement.classList.toggle("dark", dark);
  try { localStorage.setItem("candy-theme", dark ? "dark" : "light"); } catch (e) {}
}
// Theme button:  applyTheme(!document.documentElement.classList.contains("dark"))
// Follow system while user hasn't chosen:
//   matchMedia("(prefers-color-scheme: dark)").addEventListener("change", (e) => {
//     if (!localStorage.getItem("candy-theme")) applyTheme(e.matches);
//   });
```
