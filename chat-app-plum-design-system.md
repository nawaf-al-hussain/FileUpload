# Chat App Plum — Design System

> The complete design language of **Chat App Plum** (`version: alpha` — *"Messaging: plum bubbles, chat-pop, read receipts"*), written as a portable spec so it can be applied to **any** product — chat or otherwise.
> Source: supplied alpha spec (colors · typography · rounded · spacing · components + overview/do's-and-don'ts) · **Dark mode: designed here as a first-class citizen** (lights off, plum on) · Companion file to `open-notebook-design-system.md` and `candy-shop-design-system.md` — same 16-section anatomy; the trilogy is diff/swap compatible.

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

The theme is **"Chat App Plum"**: a soft violet-washed room where plum ink speaks, lavender whispers metadata, and one violet accent drives everything you can *do*. Messages arrive with a pop; receipts whisper in micro-type. It is calm where Candy Shop is loud — but it obeys the same species of discipline. The spec's own words set the laws:

> **violet acts — exactly one action per screen**
> **neutral carries the composition — negative space is a feature**
> **no gradients — this system is flat on purpose**
> **chat-pop: arrivals bounce, receipts whisper**

Unpacked into operational laws:

| # | Law | Practical meaning |
|---|-----|-------------------|
| 1 | **Violet acts** | Violet (`#7B44C7`) is the *only* interaction color — send button, links, read ticks, focus, one primary action per screen. Reserve it. |
| 2 | **Plum is the ink** | All reading text is deep plum (`#23132E`) — never black, never gray. Plum also serves as the inverse fill (tooltips, highlight cards, contained tabs). |
| 3 | **Lavender whispers** | Lavender (`#8672A0`) is the metadata voice: borders, captions, dividers, timestamps' family. It never competes with violet. |
| 4 | **Neutral is the room** | The page field is softly violet-tinted (`#F4EFFA`), not gray. White surfaces float on it. The tint IS the atmosphere — never flatten it to `#F5F5F5`. |
| 5 | **Flat on purpose** | Zero gradients. Zero shadows on anchored layout. Depth = surface shift + 1px border. Only floating layers (dialogs, popovers, toasts) cast the one sanctioned shadow. |
| 6 | **Soft, contained geometry** | Radii 10 / 18 / 28px + pill. Rounded but restrained — *chat bubble, not candy*. The floor for containers is 10px. |
| 7 | **Lights off, plum on** | Dark mode swaps ink & paper (plum-black room, lavender-white ink). The violet **fill** keeps its color in both themes — white-on-violet passes AA at 6.0:1 either way; only violet-as-*text* lightens in the dark. |
| 8 | **One family, many voices** | Inter does everything — personality comes from weight, size, and tracking, not font contrast. Numbers wear tabular figures. |
| 9 | **Receipts whisper** | Read-state micro-type (timestamps, ticks, presence) is the smallest, quietest layer in the system. It must never compete with message text for a single glance. |

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
| Font | Google Fonts: **Inter** (400/500/600/700) | One `<link>`, `display=swap`; enable `tnum` for timestamps |
| CSS engine | Plain custom properties — or Tailwind v4 via the `@theme inline` bridge | Framework-free works too |
| Icons | Lucide | `stroke-width: 2` (lighter hand than Candy Shop's 2.25) |
| Toasts | sonner (or equivalent), themed by the same variables | |
| Motion | CSS transitions + `prefers-reduced-motion` guard | The `chat-pop` keyframe is plain CSS |
| Theme state | `localStorage['plum-chat-theme']` + no-flash inline script (§16) | light / dark / system |

---

## 3. Color System

### 3.1 Core palette (the 6 owned colors)

| Token | Hex | Name | Role |
|-------|-----|------|------|
| `--plum` | `#23132E` | Deep plum | Headlines, body ink, inverse fills, outgoing-bubble-adjacent accents |
| `--lavender` | `#8672A0` | Lavender | Borders, captions, dividers, metadata, presence rings |
| `--violet` | `#7B44C7` | Violet | **THE accent** — outgoing bubbles, send button, links, read ticks, focus |
| `--mist` | `#F4EFFA` | Mist | Page foundation (light bg) and dark-mode ink |
| `--paper` | `#FFFFFF` | White | Cards, incoming bubbles, inputs |
| `--on-primary` | `#FFFFFF` | — | Text/icons on violet & plum fills (constant in both themes) |

### 3.2 Semantic tokens (the portable layer)

Components reference these **only**. Light and dark values side by side — the dark column is the designed palette, not an afterthought.

| Token | Light | Dark | Purpose |
|-------|-------|------|---------|
| `--bg` | `#F4EFFA` | `#161021` | Page canvas / chat room |
| `--surface` | `#FFFFFF` | `#221834` | Cards, incoming bubbles, inputs |
| `--surface-raised` | `#FFFFFF` | `#2C2044` | Hover planes, popovers, menus |
| `--ink` | `#23132E` | `#F4EFFA` | Primary text |
| `--muted` | `#5F4B7A` | `#B3A3CC` | Captions, timestamps, metadata (AA-safe text tier) |
| `--line` | `rgba(134,114,160,.32)` | `rgba(134,114,160,.40)` | Hairline borders, bubble strokes, dividers |
| `--line-strong` | `#8672A0` | `#8672A0` | Input borders, emphasized strokes |
| `--accent` | `#7B44C7` | `#7B44C7` | Outgoing bubbles, send button, primary action, focus |
| `--accent-hover` | `#6838AD` | `#8A55DB` | Hover fill (darker in light, lighter in dark) |
| `--accent-ink` | `#7B44C7` | `#A678EE` | Violet **as text** — links, read ticks, active states |
| `--on-accent` | `#FFFFFF` | `#FFFFFF` | Text on violet fills |
| `--focus-ring` | `#8672A0` | `#A678EE` | `:focus-visible` outline |

Three derivations are part of the system, not optional polish:

- **`--muted` light (`#5F4B7A`) is lavender deepened toward plum.** Raw lavender on mist is only ~3.8:1 — fine for borders/fills, too weak for caption-size text. The deepened value reaches ~6.7:1. Rule: raw lavender for *borders/fills*, deepened lavender for *text*.
- **`--accent-ink` splits the accent's two jobs.** As a *fill*, violet stays `#7B44C7` in both themes (white text on it = 6.0:1, comfortably AA). As *small text on the background*, violet works in light (5.3:1) but collapses in dark (3.1:1) — so dark text duty shifts to the lightened `#A678EE` (5.8:1). The bubble keeps its color; only the words about it lighten.
- **Bubbles always carry a 1px `--line` stroke** — white-on-mist and surface-on-plum-black both sit near 1.1:1 boundary contrast, which fails WCAG 1.4.11 for component boundaries. The hairline fixes it in both themes.

### 3.3 Contrast ledger (WCAG 2.1, approximate)

**Light**

| Pair | Ratio | Grade |
|------|-------|-------|
| ink `#23132E` on bg `#F4EFFA` | 15.4:1 | AAA |
| ink on surface `#FFFFFF` | 17.4:1 | AAA |
| muted `#5F4B7A` on bg | 6.7:1 | AA |
| muted on surface | 7.6:1 | AA |
| accent-ink `#7B44C7` on bg (links, read ticks) | 5.3:1 | AA |
| on-accent `#FFFFFF` on violet fill | **6.0:1** | **AA — no caveat** |
| raw lavender `#8672A0` on bg | 3.8:1 | borders/fills only, never small text |

**Dark**

| Pair | Ratio | Grade |
|------|-------|-------|
| ink `#F4EFFA` on bg `#161021` | 16.4:1 | AAA |
| ink on surface `#221834` | 15.7:1 | AAA |
| muted `#B3A3CC` on bg | 8.0:1 | AA |
| muted on surface `#2C2044` | 7.2:1 | AA |
| accent-ink `#A678EE` on bg | 5.8:1 | AA |
| on-accent on violet fill | **6.0:1** | **AA — no caveat** |
| violet fill vs dark bg (component boundary) | 3.1:1 | passes 1.4.11 non-text |

> Unlike Candy Shop, this system has **no white-on-accent caveat**: violet is dark enough that white text passes AA with room to spare, in both themes. That is the single biggest accessibility win of the palette — exploit it.

### 3.4 Color usage quick rules

- **One violet per screen:** the send button *or* the retry link *or* the primary CTA — never two competing actions. Demote extras to plum fill (inverse) or lavender outline (secondary).
- **Read ticks are the sanctioned micro-accent:** violet double-checks are metadata, not actions, and are the brand moment of a chat app. Keep them ≤14px so they whisper (Law 9).
- **No green exists** — this system owns no green. Online presence = violet dot; read receipts = violet ticks; there is no "success green" anywhere.
- **Failed messages stay neutral:** plum `AlertCircle` + caption; the *retry* affordance is the violet action (retry is interaction — correct semantics).
- Dark mode: **no pure black, no pure white text.** The plum/lavender duotone keeps the room warm at night.

---

## 4. Typography

### 4.1 Font family (1 font, weight-driven voices)

| Role | Font | Weights | Fallback stack | Rule |
|------|------|---------|----------------|------|
| **Everything** (`--font-sans`) | Inter (or Inter variable) | 400, 500, 600, 700 | "Segoe UI", "Helvetica Neue", sans-serif | Display, headings, body, UI, labels. Personality comes from weight/size/tracking — never introduce a second family. |

Inter-specific settings that are part of the system:

- **Tabular figures for anything that ticks:** timestamps, unread counts, timers — `font-feature-settings: "tnum" 1` (otherwise message times jitter as digits change).
- Optional refinement: `"cv05" 1` (lowercase l with tail) improves mixed-case message text; do not enable ligature/calt overrides.

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
```

### 4.2 Type scale

| Token | Size | Weight | Line-height | Tracking | Usage |
|-------|------|--------|-------------|----------|-------|
| `display` | 3.5rem / 56px | 700 | 1.05 | **−0.03em** (spec) | Marketing/empty-state heroes only — almost never inside the app shell |
| `h1` | 1.9rem / 30px | 700 | 1.2 | −0.02em | Page/pane titles (e.g. conversation header on wide screens) |
| `h2` | 1.35rem / 21.6px | 700 | 1.25 | −0.01em | Section headers, dialog titles *(derived)* |
| `h3` | 1.05rem / 16.8px | 600 | 1.35 | 0 | Card titles, list names *(derived)* |
| `body-lg` | 1.0625rem / 17px | 400 | 1.55 | 0 | Lead/empty-state copy *(derived)* |
| `body` | **0.95rem / 15.2px** (spec) | 400 | **1.55** (spec) | 0 | Default — message text, controls |
| `caption` | 0.8rem / 12.8px | 500 | 1.45 | 0 | Helper text, last-message preview *(derived)* |
| `label` | **0.72rem / 11.5px** (spec) | **600** (spec) | 1.4 | **+0.04em** (spec) | UPPERCASE — buttons, overlines, section eyebrows |
| `micro` | 0.68rem / 10.9px | 500 | 1.35 | 0.01em | **The whisper tier** — timestamps, read receipts, presence labels *(derived)* |

Rules: the whisper tier (`micro`) never carries information available nowhere else — pair every timestamp/receipt with `aria-label` where it matters; labels are *never* sentence case; body never below 0.95rem except `caption`/`label`/`micro`; the scale is **identical in dark mode**. Responsive: `display` drops to 2.75rem under 768px.

**Spacing between type blocks:** paragraphs/messages separated by `--space-sm` (8px); heading groups `margin-top: var(--space-lg)`, `margin-bottom: var(--space-md)`.

---

## 5. Shape — Radius

**Philosophy: soft but contained — chat bubble, not candy. The floor is 10px.**

| Token | Value | Applied to |
|-------|-------|-----------|
| `--radius-sm` | **10px** (spec) | Inputs, selects, list items, badges, tooltips, alerts, **bubble tail corner** |
| `--radius-md` | **18px** (spec) | **Buttons** (spec), **chat bubbles**, toasts, dropdown menus, images in messages |
| `--radius-lg` | **28px** (spec) | **Cards** (spec), dialogs, **composer container**, modal sheets |
| `--radius-pill` | 999px | Presence dots, unread badges, progress tracks, avatars, radio, switches |

**The bubble tail convention:** outgoing bubbles are `--radius-md` with `border-bottom-right-radius: var(--radius-sm)`; incoming mirror it (`border-bottom-left-radius`). The tail corner marks the speaker — it stays within the official scale (10px), no custom values.

Small-control exemption: controls under ~32px (checkbox ≈7px, radio/dots/avatars full-round) sit outside the scale. Everything else obeys the ladder — nearest rung, never in between.

---

## 6. Depth — Shadows

**Flat on purpose. Anything anchored to the page casts nothing — depth = surface shift + 1px border.**

| Token | Light | Dark | Used by |
|-------|-------|------|---------|
| `--shadow-pop` | `0 10px 30px -8px rgba(35,19,46,0.16)` | `0 10px 30px -8px rgba(0,0,0,0.5)` | Popovers, dropdowns, tooltips, toasts |
| `--shadow-overlay` | `0 20px 50px -12px rgba(35,19,46,0.24)` | `0 20px 50px -12px rgba(0,0,0,0.6)` | Dialogs / modal sheets |
| `--glow-accent` | *(none)* | `0 0 20px rgba(123,68,199,0.25)` | **Dark mode only:** unread badge & send button glow faintly |

Rule of thumb: anchored in the page → border only. Floats above the page → `--shadow-pop`. Blocks the page → `--shadow-overlay`. The composer bar, thread header, and conversation list are *anchored* — they separate with hairlines (`--line`), never shadows. In dark mode shadows go blacker and the faint violet glow marks the two elements that matter most (unread, send).

---

## 7. Motion

**Chat-pop: arrivals bounce, everything else stays calm.**

| Token | Value | Used for |
|-------|-------|----------|
| `--motion-fast` | 150ms | Hovers, receipt flips, fades |
| `--motion-base` | 250ms | **`chat-pop` arrival**, dialog pop, toast slide |
| `--motion-slow` | 400ms | Pane transitions, mobile nav, sheet slide |
| `--ease-out` | `cubic-bezier(0.22, 1, 0.36, 1)` | Standard entrances |
| `--ease-spring` | `cubic-bezier(0.34, 1.56, 0.64, 1)` | **The signature** — message arrivals and send-button release |

Standard motions:

- **`chat-pop` (signature):** every message bubble enters with `opacity 0→1, translateY(8px)→0, scale(0.96)→1` at 250ms `--ease-spring`. Outgoing messages pop instantly (you sent them — acknowledge the action); incoming pop only if the thread is scrolled to bottom (otherwise the unread pill appears instead — no motion you can't see).
- **Send button:** squash `scale(0.94)` on press, spring release; icon cross-fades Send→Loader (sending)→Check (sent).
- **Receipt flip:** sent→delivered→read ticks cross-fade at 150ms; the read flip to violet lags 200ms *after* the state change so it reads as a breath, not a blink.
- **Typing indicator:** three 6px dots bounce (`translateY(-3px)`) 1.2s infinite, staggered 150ms.
- **Hover:** conversation list items and buttons transition `background-color` 150ms ease-out; cards get border-strong, no lift, no shadow.
- **Pane transitions (mobile):** list ↔ thread slide at 400ms ease-out; back is the mirror.
- **Theme switch:** `background-color / color / border-color` 200ms on `body` — lights off, not a flash.
- **Reduced motion:** under `@media (prefers-reduced-motion: reduce)` — `chat-pop` and dot-bounce become opacity-only; no transforms.

---

## 8. Iconography

- Library: **Lucide**, default stroke — `stroke-width: 2` (a lighter hand than Candy Shop; chat is quick, not chunky).
- Sizes: **14px** inline (receipts, timestamps companions) · **16px** controls, composer tools · **20px** nav, thread header actions.
- Color: icons inherit `--ink` or `--muted`; **violet only for active/selected states** (send button, active tab, read ticks via `--accent-ink`).
- Icon buttons always carry `aria-label`.
- Canonical set: `Send` (the action) · `Paperclip` attach · `Smile` emoji · `Mic` voice · `Phone` / `Video` call · `Search` · `MoreVertical` overflow · `Check` / `CheckCheck` receipts · `Clock` sending · `AlertCircle` failed · `ArrowDown` scroll-to-bottom · `Sun` / `Moon` theme.

---

## 9. Dark Mode Architecture

**Strategy: class-based on `<html>`, three-state preference (light / dark / system), zero flash.**

1. **No-flash script** runs before hydration: reads `localStorage['plum-chat-theme']`, applies the `dark` class on `document.documentElement`, falls back to the system preference, swallows errors (full script in §16).
2. **Tailwind v4 variant:** `@custom-variant dark (&:where(.dark, .dark *));`
3. **Only raw carriers are overridden inside `.dark`** — semantic aliases defined once with `var()` re-resolve automatically (see §2). Never duplicate an alias into the dark block.
4. `color-scheme: light` on `:root`, `dark` under `.dark` — native scrollbars, form controls, and autofill follow the theme.
5. **The dark palette law — lights off, plum on:**
   - Paper: mist `#F4EFFA` → plum-black `#161021` (derived from the plum ink, **never `#000`**).
   - Ink: plum `#23132E` → mist `#F4EFFA`.
   - Violet **fill** is byte-identical in both themes (`#7B44C7`) — outgoing bubbles and the send button keep their color at night; white-on-violet stays 6.0:1. Only hover and violet-as-text shift: hover lightens (`#8A55DB`), text lightens (`#A678EE`).
   - Lavender `#8672A0` keeps border duty; text duty moves to lightened `#B3A3CC`.
   - Shadows go blacker; unread badge and send button gain `--glow-accent`.
6. **Toggle UI:** Sun/Moon icon button in the thread header (Sun rotates/scales out, Moon rotates in); optional Light/Dark/System menu with the active option marked in `--accent-ink`.

---

## 10. Component Specifications

Every spec below consumes semantic tokens only — no raw hex in components. If you use React + shadcn-style primitives, paste these into cva variants; otherwise copy the declarations literally.

### 10.1 Button

| Variant | Fill | Text | Border | Hover | Active |
|---------|------|------|--------|-------|--------|
| **primary** (spec) | `--accent` | `--on-accent` | none | `--accent-hover` | `scale(0.97)` |
| **secondary** | `--surface` | `--ink` | 1.5px `--line-strong` | bg `--surface-raised`, border `--muted` | `scale(0.97)` |
| **ghost** | transparent | `--muted` | none | bg `--surface-raised`, text `--ink` | `scale(0.97)` |
| **inverse** | `--ink` (plum / mist in dark) | `--bg` | none | `opacity: .9` | `scale(0.97)` |

- **Shape & type (from the spec):** `border-radius: var(--radius-md)`; `padding: 12px 20px`; text in the `label` style (Inter 0.72rem / 600 / uppercase / 0.04em).
- **Sizes:** sm `padding: 8px 14px` · md (spec default) · lg `padding: 14px 24px` for dialogs/empty states.
- **Focus:** `outline: 2px solid var(--focus-ring); outline-offset: 2px`. **Disabled:** `opacity: .4; pointer-events: none`.
- White-on-violet is 6.0:1 — this system's primary button needs **no accessibility caveat** (see §13).
- The one-violet rule: one primary button visible per screen or region.

### 10.2 Card (spec component)

- Base (from the spec): `background: var(--surface); color: var(--ink); border-radius: var(--radius-lg); padding: 24px;` plus `border: 1px solid var(--line)`.
- The spec's **24px padding is canonical** — it sits deliberately between md (16) and lg (32); don't "fix" it.
- Variants: **plain** · **interactive** (hover: border `--line-strong`, bg `--surface-raised` in dark; no lift, no shadow) · **selected** (2px `--accent` border) · **inverse** (`--ink` fill, `--bg` text — profile/stat highlights).
- Header slot: `h3` title + `caption` metadata in `--muted`.

### 10.3 Chat Bubble (signature component)

| Property | Outgoing (mine) | Incoming (theirs) |
|----------|-----------------|-------------------|
| Fill | `--accent` (violet, both themes) | `--surface` |
| Text | `--on-accent` (white) | `--ink` |
| Radius | `--radius-md`, tail = `border-bottom-right-radius: var(--radius-sm)` | `--radius-md`, tail = `border-bottom-left-radius: var(--radius-sm)` |
| Border | none | 1px `--line` |
| Padding | `10px 14px` | `10px 14px` |
| Max-width | `min(75%, 480px)` | `min(75%, 480px)` |
| Alignment | right (margin-left: auto) | left |

- Text: `body` 0.95rem/1.55; links inside bubbles underlined, violet in incoming (`--accent-ink`), white-underlined in outgoing.
- **System bubble variant:** centered chip, bg `--surface-raised`, `micro` text in `--muted`, radius pill — for "Alice joined the room".
- Failed variant: outgoing keeps violet fill at 40% desaturation is **forbidden** (no opacity tricks on brand) — instead the bubble gains a plum `AlertCircle` footer row and the receipt becomes the retry link.
- Bubbles enter with `chat-pop` (§7) and group per §12.2.

### 10.4 Composer (message input bar)

- Container: `--surface`, `--radius-lg` (28px), `padding: 8px 8px 8px 16px`, 1px `--line` border, anchored to the thread bottom (hairline separation, no shadow).
- Text field: borderless inside the container, `body` size, placeholder `--muted` ("Message…"); grows to 5 lines max then scrolls.
- Tools: `Paperclip`, `Smile`, `Mic` as 36px ghost icon buttons (`--muted`, hover `--ink` on `--surface-raised`).
- **Send:** 40px circle, `--accent` fill, white `Send` 18px — **this is usually the screen's one violet action**; squash 0.94 + spring release; disabled state = `--surface-raised` fill with `--muted` icon when the input is empty.
- `Enter` sends, `Shift+Enter` newlines (document it in the placeholder tooltip).

### 10.5 Read Receipts & Message Status (the whisper tier)

| State | Icon | Color | Micro-copy |
|-------|------|-------|-----------|
| Sending | `Clock` | `--muted` | — |
| Sent | `Check` | `--muted` | "Sent" |
| Delivered | `CheckCheck` | `--muted` | "Delivered" |
| **Read** | `CheckCheck` | **`--accent-ink`** | "Read" |
| Failed | `AlertCircle` | `--ink` + retry link in `--accent-ink` | "Not delivered · Retry" |

- Icons 14px, micro text 0.68rem, `tnum` figures; sits under the last bubble of a group, right-aligned for outgoing.
- The violet read tick is the **sanctioned micro-accent** (metadata exception, §3.4) — never enlarge it, never animate it more than the 150ms cross-fade + 200ms violet lag.
- Always provide `aria-label="Read at 14:32"` — the whisper tier must not be the only carrier of state.

### 10.6 Typing Indicator & Presence

- **Typing:** an incoming-style bubble containing three 6px `--muted` dots, bounce-staggered (§7); `aria-live="polite"` label "Alice is typing…".
- **Presence:** 10px dot pinned to the avatar's bottom-right with a 2px ring of the host surface: **online = `--accent` fill**, away = `--lavender`, offline = hollow (`--surface` fill, 1.5px `--line-strong` ring). No green exists (§3.4).

### 10.7 Avatar

- Sizes: 24 (inline mentions) · 36 (list) · 44 (thread header) · 80 (profile).
- Shape: full circle (`--radius-pill`); image cover; fallback = initials on `--surface-raised` with `--muted` 600 text.
- Group avatar stacks offset −8px with a 2px `--bg` ring.

### 10.8 Input & Textarea (forms / settings)

- `background: var(--surface); border: 1.5px solid var(--line-strong); border-radius: var(--radius-sm); padding: 10px 14px; font: 400 0.95rem/1.55 var(--font-sans); color: var(--ink);`
- Placeholder `--muted`. **Focus:** border `--accent` + `box-shadow: 0 0 0 3px color-mix(in srgb, var(--accent) 20%, transparent)`.
- **Error:** border `--accent` is *not* used (violet means action, not error) — errors use 1.5px `--ink` border + `caption` message with `AlertCircle`; the field's helper text flips to `--ink` 600. (Semantic discipline over convention; document it.)
- Textarea: same spec, `min-height: 88px`. Input height ≥44px on touch.

### 10.9 Select & Menus

Trigger = Input spec + `ChevronDown` 16px `--muted`. Menu: `--surface-raised`, `--radius-sm`, `--shadow-pop`, border `--line`; items `padding: 8px 14px`, hover bg `--surface-raised` (light) / `--surface` (dark); **selected** item text `--accent-ink` + trailing `Check` 16px.

### 10.10 Checkbox, Radio, Switch

- **Checkbox:** 20px box, 7px radius (small-control exemption); checked = `--accent` fill + white `Check`; unchecked = 1.5px `--line-strong` on `--surface`.
- **Radio:** 20px circle; checked dot `--accent`.
- **Switch:** 40×22 track, `--radius-pill`; off = `--line-strong` track, on = `--accent` track (with `--glow-accent` in dark); white knob, 250ms `--ease-spring`.

### 10.11 Thread Header & Conversation List

- **Thread header:** 64px bar, `--bg` fill, 1px `--line` bottom hairline; avatar 44 + name `h3` + presence `micro`; actions (Phone, Video, Search, theme toggle) as 36px ghost icon buttons. Sticky top; no shadow.
- **Conversation list item:** 72px min-height, `--radius-sm`, padding 12px; avatar 36 + name `body` 600 + last-message `caption` in `--muted` + time `micro` `tnum`; hover bg `--surface` (light) / `--surface-raised` (dark); **active** bg `--surface` + 1px `--line` + 3px `--accent` left spine.
- **Unread badge:** pill on `--accent`, white `micro` 600 `tnum`, `min-width: 20px`; in dark it glows (`--glow-accent`).
- Section eyebrows ("PINNED", "ALL") use `label` style in `--muted`.

### 10.12 Badge & Chip

- **Badge:** `label` style, `--radius-pill`, `padding: 3px 10px`. Neutral: bg `--bg`, text `--muted`, 1px `--line` (dark: bg `--surface-raised`). Violet badge: `--accent` fill / white text — for unread counts and "NEW" flags only.
- **Chip:** `caption` text, `--radius-pill`, border `--line-strong`, removable `X` 14px, hover bg `--surface-raised`.

### 10.13 Dialog

- Panel: `--surface`, `--radius-lg`, `padding: var(--space-lg)` (32px), max-width 440px, `--shadow-overlay`; pop animation per §7.
- Overlay: `rgba(35,19,46,0.45)` light / `rgba(8,4,14,0.6)` dark; optional `backdrop-filter: blur(2px)`.
- Title `h2`; body `body`; actions right-aligned — **at most one primary**. Close `X` 16px `--muted`, top-right.
- Mobile: bottom sheet, radius lg on top corners only, 400ms slide.

### 10.14 Popover & Tooltip

- **Popover:** `--surface-raised`, `--radius-sm`, `--shadow-pop`, border `--line`.
- **Tooltip:** inverse — bg `--ink`, text `--bg`, `--radius-sm`, `caption` 500, `padding: 6px 10px`; fades 150ms. In dark: mist tooltip with plum text — the swap is the charm.

### 10.15 Toast

- `--surface-raised`, `--radius-md`, `--shadow-pop`, border `--line`, `padding: var(--space-md)`; slide-up 16px + fade, auto-dismiss 5s.
- Title `caption` 600 in `--ink`; description `caption` in `--muted`; `AlertCircle`/`Check` icon per §10.5 semantics.

### 10.16 Link, Progress, Skeleton, Separator

- **Links:** `--accent-ink`, underlined, `text-underline-offset: 3px`, thickness 1.5px; hover brightens (dark) / stays (light). Links are wayfinding, not actions — no violet-budget cost, but keep them sparse.
- **Progress:** track 6px `--radius-pill` in `--line`; fill `--accent` — sanctioned here because upload progress in a chat *is* the user's active intent; it still counts toward the one-violet audit.
- **Skeleton:** bg `--surface-raised`, `--radius-sm`, pulse per §7; incoming-bubble skeletons = 3 rounded bars of varying width. Never gray — the plum family only.
- **Separator:** 1px `--line`.

---

## 11. Layout System

This is an **app shell**, not a page: full viewport height, internal scroll regions.

| Token | Value | Notes |
|-------|-------|-------|
| `--list-w` | 320px | Conversation list pane (fixed) |
| `--thread-w` | 760px | Thread content max-width, centered in its pane |
| `--details-w` | 280px | Optional right details pane (≥1280 only) |
| Gutter | `--space-md` (16px) | Outer padding |
| Bubble gap | 4px within a group · 16px between groups · 24px between days | See §12.2 |

- **Panes:** ≥1280 — list + thread + details · ≥1024 — list + thread · ≥768 — list + thread · <768 — single pane, list ↔ thread slide transitions with a back affordance in the header.
- **Thread anatomy (top to bottom):** header 64px sticky · scroll region `flex-1` (the only scroller) · composer anchored bottom. Day dividers and unread dividers inline (§12).
- **Scroll-to-bottom:** 36px circle, `--surface` fill, 1px `--line`, `--shadow-pop`, `ArrowDown` 16px; shows a violet unread-count pill when messages arrive off-bottom.
- **Spacing:** section gap `--space-lg` (32px); pane internal padding `--space-md`.
- **Breakpoints:** 640 / 768 / 1024 / 1280.
- **Z-index ladder:** dropdown 1000 · sticky header/composer 1100 · overlay 1200 · modal 1300 · toast 1400 · tooltip 1500.

---

## 12. Application Patterns

### 12.1 The one-violet audit (run before shipping)
List every accent-colored element on the screen. Exactly **one** may be a call to action (usually the send button). Sanctioned non-action violets: read ticks (`--accent-ink`, ≤14px), active list spine, links, focus rings (don't count). Demotions: extra CTAs → `inverse`/`secondary`; progress → fill only when it's the user's own upload; badges → neutral. If the screen feels under-accented, add whitespace — never a second violet.

### 12.2 Bubble grouping & day dividers
Consecutive messages from one sender **group**: 4px gaps inside a group, only the last bubble carries the tail corner, sender name + avatar appear once at the top of the group. 16px between different senders, 24px around a day divider. Day divider = centered `micro` label on `--surface-raised` pill with 1px `--line` rails — e.g. "TODAY". Never re-render the whole thread with animation on load; only new messages `chat-pop`.

### 12.3 Read-state micro-type (the whisper tier, in practice)
Timestamps and receipts live in `micro` 0.68rem with `tnum` figures, positioned under the last bubble of a group — never beside every message. In conversation lists, times sit top-right of each item. The whisper tier is metadata: if you're tempted to make it bigger for emphasis, the emphasis belongs in message text instead.

### 12.4 Unread divider
A 1px `--accent` hairline across the thread with a centered `micro` violet label ("3 NEW") — the one place a violet line may span the layout. It scrolls away naturally; don't pin it.

### 12.5 System messages
Centered `micro` chips on `--surface-raised`, radius pill, `--muted` text: "Alice joined", "Chat renamed to Design". No icons needed; never violet — system events are not actions.

### 12.6 Empty states
- **No conversations:** mist field, `display`-sized greeting ("Good evening."), one `body-lg` line in `--muted`, one primary button (the screen's violet). Whitespace is the decoration.
- **Empty thread:** centered avatar + "Say hi to Alice" `h3` + suggestion chips (`caption`, border `--line-strong`, hover raise). Tapping a chip fills the composer — it doesn't send.

### 12.7 Loading
Thread history loads as 3-bar incoming-bubble skeletons (§10.16) alternating sides; sending a message shows the optimistic bubble immediately (full violet) with a `Clock` receipt — never a spinner in place of the bubble. Send button icon cross-fades while in flight.

### 12.8 Links, mentions & code in messages
Links: §10.16 (violet in incoming, white-underlined in outgoing). **Mentions:** @name in `--accent-ink` 600, no underline, bg `color-mix(in srgb, var(--accent) 12%, transparent)`, radius 6px; your own mention gets the 1.5px `--accent` border. Inline code: `--surface-raised` bg, `--radius-sm`, 0.85em, `tnum`. Long URLs truncate with ellipsis at the bubble's max-width.

### 12.9 Optimistic state & failure recovery
Outgoing message lifecycle: optimistic bubble (violet, `Clock`) → `Check` → `CheckCheck` muted → `CheckCheck` violet (read). On failure the bubble stays, receipt becomes "Not delivered · Retry" (§10.5); tapping Retry re-queues and replays `chat-pop` only on success. Never auto-delete a failed bubble.

---

## 13. Accessibility

- **Focus everywhere:** `:focus-visible { outline: 2px solid var(--focus-ring); outline-offset: 2px; }` on every interactive element. Never `outline: none` without a replacement ring.
- **Contrast:** ledger in §3.3 — every pair AA or better in both themes, **including white-on-violet (6.0:1)**. This system has no button caveat; the two engineered fixes (`--muted` deepened lavender, `--accent-ink` dark variant) are already baked into the tokens.
- **Never color alone:** message status pairs icons + micro-copy with color; presence dots get `aria-label` ("Online"); the violet read tick carries `aria-label="Read at HH:MM"`.
- **Live regions:** new messages and typing indicators announce via `aria-live="polite"`; never move focus on arrival.
- **Targets:** ≥44×44px on touch (composer tools 36px visual + padding hit-area; list items 72px).
- **Reduced motion:** `chat-pop` and typing dots collapse to opacity-only (§7).
- **The whisper tier:** `micro` type (10.9px) is below WCAG's readable-minimum guidance for *essential* text — that's why every whisper element pairs with `aria-label`/`title` and never carries sole-critical information.
- **Forms:** errors announced via `aria-describedby`; labels visible — placeholder-only inputs banned.

---

## 14. Do & Don't

**Do**

- **Do** use Tertiary for exactly one action per screen. *(spec)*
- **Do** let Neutral carry the composition — negative space is a feature. *(spec)*
- Do keep violet fills identical across themes — white-on-violet passes AA both ways (6.0:1); only violet-as-text lightens in dark.
- Do keep timestamps and receipts in the whisper tier with `tnum` figures — they inform, never shout.
- Do group messages (4px/16px/24px rhythm) and reserve the tail corner for the group's last bubble.

**Don't**

- **Don't** introduce gradients. This system is flat on purpose. *(spec)*
- **Don't** mix Tertiary with alternate accents; the single-accent rule is load-bearing. *(spec)*
- Don't reach for pure `#000` pages in dark mode — plum-black `#161021` keeps the violet warmth; and no pure-white text on dark surfaces (mist ink is the voice).
- Don't use gray metadata text — muted is always plum-family (`#5F4B7A` light / `#B3A3CC` dark), never cool grays.
- Don't use green for presence or success — online is violet, read is violet, failure is plum + violet retry. There is no green in this universe.
- Don't fade, shrink, or desaturate failed bubbles — keep them honest and let the retry link (violet) be the recovery action.

---

## 15. Porting Guide — Apply to Any Website

1. **Copy the CSS** from §16 into your global stylesheet (works with or without Tailwind — plain custom properties) and add the Inter `<link>` from §4.1.
2. **Map type roles:** Inter everywhere; `label` uppercase 600 with 0.04em; `micro` + `tnum` reserved for anything that ticks; `tnum` on every counter.
3. **Wire the theme switch:** `dark` class on `<html>`, the no-flash script, only raw carriers overridden inside `.dark`. Persist to `localStorage['plum-chat-theme']`; default to system.
4. **Tailwind v4:** paste the `@theme inline` bridge — `bg-accent`, `text-ink`, `rounded-md`, `font-sans` work instantly. **Tailwind v3:** use the compact config in §16. **Plain CSS / other frameworks:** reference `var(--…)` directly; the utility classes at the end of §16 cover the chat shell's 90%.
5. **Rebuild components from §10** — every value is a token reference; if you ever type a hex inside a component, you've broken the architecture.
6. **Respect the laws (§1)** — the calm collapses without the discipline. When in doubt: fewer accents, quieter metadata, softer radii, flatter surfaces.
7. **Smoke test:** send a message (optimistic violet bubble pops, receipt walks Clock→Check→CheckCheck), toggle dark (bubbles keep violet; only violet text lightens), receive a message off-bottom (unread pill, no invisible motion), tab through (lavender/violet rings everywhere), resize 768 (single-pane slide).

---

## 16. Appendix — Complete Copy-Paste CSS

The entire token layer, self-contained and framework-agnostic (Tailwind bridges included separately at the end). Drop into your global stylesheet.

```css
/* ============ CHAT APP PLUM — tokens ============ */

:root {
  color-scheme: light;

  /* — Layer 1a: brand constants (identical in both themes) — */
  --plum: #23132E;
  --lavender: #8672A0;
  --violet: #7B44C7;
  --mist: #F4EFFA;
  --white: #FFFFFF;

  /* — Layer 1b: raw carriers (the ONLY things overridden in .dark) — */
  --raw-bg: #F4EFFA;
  --raw-paper: #FFFFFF;
  --raw-paper-raised: #FFFFFF;
  --raw-ink: #23132E;
  --raw-muted: #5F4B7A;      /* lavender deepened for AA text */
  --raw-line-alpha: 0.32;
  --raw-accent-hover: #6838AD;
  --raw-accent-ink: #7B44C7; /* violet passes as text on light bg */
  --raw-focus: #8672A0;

  /* — Layer 2: semantic aliases (defined ONCE; re-resolve in dark) — */
  --bg: var(--raw-bg);
  --surface: var(--raw-paper);
  --surface-raised: var(--raw-paper-raised);
  --ink: var(--raw-ink);
  --muted: var(--raw-muted);
  --line: rgba(134, 114, 160, var(--raw-line-alpha));
  --line-strong: var(--lavender);
  --accent: var(--violet);
  --accent-hover: var(--raw-accent-hover);
  --accent-ink: var(--raw-accent-ink);
  --on-accent: #FFFFFF;
  --focus-ring: var(--raw-focus);
  --overlay: rgba(35, 19, 46, 0.45);

  /* shape (spec) */
  --radius-sm: 10px;  --radius-md: 18px;  --radius-lg: 28px;  --radius-pill: 999px;

  /* spacing (spec: sm 8 / md 16 / lg 32; xs-xl derived) */
  --space-xs: 4px;  --space-sm: 8px;  --space-md: 16px;
  --space-lg: 32px; --space-xl: 64px;

  /* motion */
  --motion-fast: 150ms;  --motion-base: 250ms;  --motion-slow: 400ms;
  --ease-out: cubic-bezier(0.22, 1, 0.36, 1);
  --ease-spring: cubic-bezier(0.34, 1.56, 0.64, 1);

  /* the only sanctioned shadows (floating layers) */
  --shadow-pop: 0 10px 30px -8px rgba(35, 19, 46, 0.16);
  --shadow-overlay: 0 20px 50px -12px rgba(35, 19, 46, 0.24);

  /* chat shell layout */
  --list-w: 320px;  --thread-w: 760px;  --details-w: 280px;

  /* type */
  --font-sans: "Inter", "Segoe UI", "Helvetica Neue", sans-serif;
}

.dark {
  color-scheme: dark;
  /* lights off, plum on — violet fill keeps its color */
  --raw-bg: #161021;
  --raw-paper: #221834;
  --raw-paper-raised: #2C2044;
  --raw-ink: #F4EFFA;
  --raw-muted: #B3A3CC;
  --raw-line-alpha: 0.40;
  --raw-accent-hover: #8A55DB;
  --raw-accent-ink: #A678EE;
  --raw-focus: #A678EE;
  --overlay: rgba(8, 4, 14, 0.60);
  --shadow-pop: 0 10px 30px -8px rgba(0, 0, 0, 0.5);
  --shadow-overlay: 0 20px 50px -12px rgba(0, 0, 0, 0.6);
  --glow-accent: 0 0 20px rgba(123, 68, 199, 0.25);
}

/* ============ base ============ */
*, *::before, *::after { box-sizing: border-box; }

body {
  margin: 0;
  background: var(--bg);
  color: var(--ink);
  font-family: var(--font-sans);
  font-size: 0.95rem;
  line-height: 1.55;
  transition: background-color 200ms var(--ease-out), color 200ms var(--ease-out),
              border-color 200ms var(--ease-out);
}

h1, h2, h3 { font-weight: 700; }
h1 { font-size: 1.9rem;   letter-spacing: -0.02em; line-height: 1.2; }
h2 { font-size: 1.35rem;  letter-spacing: -0.01em; line-height: 1.25; }
h3 { font-size: 1.05rem;  font-weight: 600; line-height: 1.35; }
.display { font-size: 3.5rem; font-weight: 700; letter-spacing: -0.03em; line-height: 1.05; }

.label { font-family: var(--font-sans); font-size: 0.72rem; font-weight: 600; letter-spacing: 0.04em; text-transform: uppercase; line-height: 1.4; }
.caption { font-size: 0.8rem; font-weight: 500; line-height: 1.45; color: var(--muted); }
.micro { font-size: 0.68rem; font-weight: 500; letter-spacing: 0.01em; line-height: 1.35; color: var(--muted); font-feature-settings: "tnum" 1; }
.tnum { font-feature-settings: "tnum" 1; }

:focus-visible { outline: 2px solid var(--focus-ring); outline-offset: 2px; }

/* ============ component recipes ============ */
.btn {
  display: inline-flex; align-items: center; gap: 8px; border: 0; cursor: pointer;
  border-radius: var(--radius-md); padding: 12px 20px;
  font-family: var(--font-sans); font-size: 0.72rem; font-weight: 600;
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
.btn-lg { padding: 14px 24px; }

.card { background: var(--surface); color: var(--ink); border: 1px solid var(--line); border-radius: var(--radius-lg); padding: 24px; }
.card-interactive { cursor: pointer; transition: background-color var(--motion-fast) var(--ease-out), border-color var(--motion-fast) var(--ease-out); }
.card-interactive:hover { border-color: var(--line-strong); }
.card-selected { border: 2px solid var(--accent); }
.card-inverse { background: var(--ink); color: var(--bg); border-color: transparent; }

/* — chat bubbles (the signature) — */
.bubble { max-width: min(75%, 480px); padding: 10px 14px; font-size: 0.95rem; line-height: 1.55; }
.bubble-out { background: var(--accent); color: var(--on-accent);
  border-radius: var(--radius-md); border-bottom-right-radius: var(--radius-sm);
  margin-left: auto; }
.bubble-in { background: var(--surface); color: var(--ink); border: 1px solid var(--line);
  border-radius: var(--radius-md); border-bottom-left-radius: var(--radius-sm); }
.bubble-system { background: var(--surface-raised); color: var(--muted);
  border-radius: var(--radius-pill); padding: 4px 12px;
  font-size: 0.68rem; letter-spacing: 0.01em; margin-inline: auto; }

.chat-pop { animation: chat-pop var(--motion-base) var(--ease-spring); }
@keyframes chat-pop {
  from { opacity: 0; transform: translateY(8px) scale(0.96); }
  to   { opacity: 1; transform: translateY(0) scale(1); }
}

.receipt { display: inline-flex; align-items: center; gap: 4px;
  font-size: 0.68rem; color: var(--muted); font-feature-settings: "tnum" 1; }
.receipt-read { color: var(--accent-ink); }

.typing { display: inline-flex; gap: 4px; padding: 12px 14px; }
.typing span { width: 6px; height: 6px; border-radius: var(--radius-pill);
  background: var(--muted); animation: typing-bounce 1.2s var(--ease-out) infinite; }
.typing span:nth-child(2) { animation-delay: 150ms; }
.typing span:nth-child(3) { animation-delay: 300ms; }
@keyframes typing-bounce {
  0%, 60%, 100% { transform: translateY(0); }
  30% { transform: translateY(-3px); }
}

/* — composer — */
.composer { display: flex; align-items: flex-end; gap: 8px;
  background: var(--surface); border: 1px solid var(--line);
  border-radius: var(--radius-lg); padding: 8px 8px 8px 16px; }
.composer-field { flex: 1; border: 0; background: transparent; color: var(--ink);
  font: 400 0.95rem/1.55 var(--font-sans); resize: none; outline: none; }
.composer-field::placeholder { color: var(--muted); }
.send-btn { width: 40px; height: 40px; border-radius: var(--radius-pill); border: 0;
  background: var(--accent); color: var(--on-accent); cursor: pointer;
  display: grid; place-items: center;
  transition: transform var(--motion-fast) var(--ease-out), background-color var(--motion-fast) var(--ease-out); }
.send-btn:hover { background: var(--accent-hover); }
.send-btn:active { transform: scale(0.94); transition-timing-function: var(--ease-spring); }
.send-btn:disabled { background: var(--surface-raised); color: var(--muted); }

/* — forms & misc — */
.input { width: 100%; background: var(--surface); color: var(--ink);
  border: 1.5px solid var(--line-strong); border-radius: var(--radius-sm);
  padding: 10px 14px; font: 400 0.95rem/1.55 var(--font-sans); }
.input::placeholder { color: var(--muted); }
.input:focus { outline: none; border-color: var(--accent);
  box-shadow: 0 0 0 3px color-mix(in srgb, var(--accent) 20%, transparent); }

.link { color: var(--accent-ink); text-decoration: underline; text-underline-offset: 3px; text-decoration-thickness: 1.5px; }
.mention { color: var(--accent-ink); font-weight: 600; border-radius: 6px;
  background: color-mix(in srgb, var(--accent) 12%, transparent); padding: 0 4px; }

.divider { border: 0; height: 1px; background: var(--line); }
.unread-divider { height: 1px; background: var(--accent); }

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
  .chat-pop, .typing span { animation: none; opacity: 1; }
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
  --color-lavender: var(--lavender);
  --color-violet: var(--violet);
  --color-mist: var(--mist);
  --radius-sm: 10px;  --radius-md: 18px;  --radius-lg: 28px;
  --font-sans: "Inter", "Segoe UI", sans-serif;
}
/* → utilities unlocked: bg-accent, text-ink, text-muted, border-line-strong,
   rounded-md, rounded-lg, dark:bg-… */
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
        plum: "#23132E", lavender: "#8672A0", violet: "#7B44C7", mist: "#F4EFFA",
      },
      borderRadius: { sm: "10px", md: "18px", lg: "28px", pill: "999px" },
      fontFamily: { sans: ["Inter", "Segoe UI", "sans-serif"] },
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
      var t = localStorage.getItem("plum-chat-theme");
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
  try { localStorage.setItem("plum-chat-theme", dark ? "dark" : "light"); } catch (e) {}
}
// Theme button:  applyTheme(!document.documentElement.classList.contains("dark"))
// Follow system while user hasn't chosen:
//   matchMedia("(prefers-color-scheme: dark)").addEventListener("change", (e) => {
//     if (!localStorage.getItem("plum-chat-theme")) applyTheme(e.matches);
//   });
```
