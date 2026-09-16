---
name: work.patpadgett.com — The Session
description: A résumé read off a green-phosphor terminal; the shell is the frame, the record is the content, every command on screen is a real one.
colors:
  crt: "#060907"
  crt-2: "#0a0f0b"
  phosphor: "#3dff73"
  phosphor-70: "#63e68b"
  phosphor-40: "#22a04a"
  phosphor-15: "#0c3a1a"
  phosphor-06: "#0a1f10"
  fg: "#c9f7d3"
  amber: "#ffb000"
  amber-dim: "#a86f00"
typography:
  display:
    fontFamily: "VT323, IBM Plex Mono, monospace"
    fontSize: "clamp(3.4rem, 9vw, 6.6rem)"
    fontWeight: 400
    lineHeight: 0.84
    letterSpacing: "0.01em"
  name:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "clamp(1.35rem, 2.2vw, 1.75rem)"
    fontWeight: 600
    letterSpacing: "0.02em"
  headline:
    fontFamily: "VT323, IBM Plex Mono, monospace"
    fontSize: "clamp(2rem, 3.4vw, 2.6rem)"
    fontWeight: 400
    lineHeight: 1
  title:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "1.05rem"
    fontWeight: 600
    lineHeight: 1.35
  body:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.6
  small:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "0.95rem"
    fontWeight: 400
    lineHeight: 1.5
  ui:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "0.9rem"
    fontWeight: 400
    lineHeight: 1.5
  caption:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "0.85rem"
    fontWeight: 400
    lineHeight: 1.5
  label:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "0.8rem"
    fontWeight: 600
    letterSpacing: "0.06em"
  lede:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "1.1rem"
    fontWeight: 400
    lineHeight: 1.55
  h2:
    fontFamily: "VT323, IBM Plex Mono, monospace"
    fontSize: "clamp(2.6rem, 5vw, 3.6rem)"
    fontWeight: 400
    lineHeight: 1
  metric:
    fontFamily: "VT323, IBM Plex Mono, monospace"
    fontSize: "clamp(2.6rem, 4vw, 3rem)"
    fontWeight: 400
    lineHeight: 0.9
rounded:
  none: "0"
spacing:
  bar: "2.25rem"
  gutter: "clamp(1rem, 4vw, 3.5rem)"
  section: "clamp(3rem, 8vw, 6rem)"
  row: "1.5rem"
  col: "100ch"
components:
  button:
    backgroundColor: "{colors.phosphor}"
    textColor: "{colors.crt}"
    typography: "{typography.label}"
    rounded: "{rounded.none}"
    padding: "0.75rem 1.25rem"
  status-cell:
    backgroundColor: "{colors.phosphor-15}"
    textColor: "{colors.phosphor}"
    typography: "{typography.small}"
    height: "{spacing.bar}"
  input:
    backgroundColor: "{colors.crt}"
    textColor: "{colors.fg}"
    typography: "{typography.body}"
    rounded: "{rounded.none}"
    padding: "0.6rem 0.75rem"
  file-row:
    textColor: "{colors.phosphor}"
    typography: "{typography.body}"
    padding: "0.55rem 0.5rem"
    minHeight: "2.5rem"
---

# Design System: work.patpadgett.com — The Session

## Overview

**Creative North Star: "The Session"**

The page is a logged-in shell on a green-phosphor monitor, and the résumé is what the shell prints. The visitor arrives on `patpadgett.com (ttyS0)`, a prompt types `finger pat`, and the answer is the person: name, role, one proof sentence, the résumé to download. Each section below is another command's output — `last` for the work record, `ls /usr/local/bin` for skills, `wall` for what colleagues wrote, `man corkscrew` for the open-source work, `mail` for contact. The commands are theatre; the labels the reader navigates by are not. Nav and headings say About, Experience, Skills, Recommendations, Corkscrew, Contact — plain English — and the typed command sits above each as flavour, `aria-hidden`.

Owner decision (critique #1): keep the terminal. The earlier "Press Sheet" system was never shipped and is retired; this document describes what is live.

**Key characteristics**
- Two phosphors only: green for the machine and the record, amber for the human's emphasis (metrics, dates, the command being typed, the PDF cell). No third hue.
- One display face (VT323) for what must be read from across the room — the four-word role, section titles, metrics. IBM Plex Mono for everything a person reads closely. Mono is the material here, not a costume: this is a terminal.
- Depth is glow, not shadow: `--glow` / `--aglow` text-shadows on phosphor-bright text, a soft box glow on the one filled button. Nothing else lifts off the glass.
- Motion is the machine working: a type-on for each command, an `opacity` "print" for the output it produces. One authored moment per section, sequenced, never a fade-up on everything. Fully gated behind `.js` and `prefers-reduced-motion`.
- Proof first. The first viewport at every width carries: name (600, 1.35–1.75rem), role (display), the Sprint/Tampa proof sentence, and the filled **Download résumé (PDF)** button with Word / Markdown beside it. The login theatre is two lines, not six.

## Colors

- **CRT** (#060907) page ground; **CRT-2** (#0a0f0b) inset panels (form).
- **Phosphor** (#3dff73) links, headings, the record's key facts, the filled button ground. 12.6:1 on CRT.
- **Phosphor-70** (#63e68b) secondary text: org names, captions, the banner. 9.8:1.
- **Phosphor-40** (#22a04a) rules that must be seen, list bullets, underline tint. Not for text.
- **Phosphor-15** (#0c3a1a) the status bar ground, hairline rules, the form border. **Phosphor-06** section tints.
- **FG** (#c9f7d3) body copy — green-white so long passages don't buzz. 15.4:1.
- **Amber** (#ffb000) metrics, dates, the typed command, `Résumé PDF` in the bar, error text, hover on the button. 10.1:1 on CRT. **Amber-dim** for the amber theme's secondary.

**The Two-Phosphor Rule.** Green is the system, amber is the operator's pen. A fact is never coloured for decoration; amber marks what the eye should land on (a number, a date, the command that produced this output) and nothing else.

**Hover inversion.** Interactive rows and cells invert to phosphor ground / CRT text (`.status a:hover`, `.file:hover`). The inverted text is the CRT colour, so 12.6:1 is preserved; detectors that read the child's default colour against the hover ground report a false 1.0:1.

## Typography

**Display:** VT323 400 — the four stacked words of the role, `h2`s, the three metric numbers. Bitmap character; glow of the matching phosphor.
**Body / UI:** IBM Plex Mono 400/600 — copy at 1rem/1.6, measure ≤ 78ch; titles 600; labels 600 uppercase 0.06em.

**Hierarchy:** name (Plex 600, 1.35–1.75rem, FG) → role (VT323 display, one word per line, word 2 amber) → proof sentence (body, 48ch balance) → download row → frame note (Phosphor-70, 0.95rem).

**The One-Word Line Rule.** The role sets one word per line at leading 0.84. It never sets a sentence.
**The Real Command Rule.** Every `.cmd` on the page is a valid shell command whose output plausibly is the section beneath it. No made-up flags.

## Layout

Full-bleed CRT; content in a `100ch` column with gutter `clamp(1rem, 4vw, 3.5rem)`. A 2.25rem sticky status bar (tmux-style) holds `[pat@patpadgett]`, six section cells, a clock at ≥60rem, and the amber `Résumé PDF` cell. Under 48rem the home cell hides, the cells scroll horizontally with a sticky amber `›` end-cap over a gradient so the reader knows there's more; every visible label is a whole word.

Hero: single column to 60rem; above it a 1fr / 22rem grid with the framebuffer portrait and three metrics stacked in the right column. File rows (`ls -lh`) are a 9.5ch / 6ch / `minmax(0,1fr)` grid; under 30rem the permission column drops and filenames wrap by `overflow-wrap: anywhere`. Nothing on the page may exceed viewport width; `overflow-x: hidden` is not a fix.

Sections open on a 1px Phosphor-15 rule with `clamp(3rem, 8vw, 6rem)` above. Jobs are 14ch date column / content column at ≥48rem.

## Elevation & Depth

Glow, not shadow. `--glow` on phosphor-bright text and the download button; `--aglow` on amber. Scanlines (`.tube::before`, repeating gradient at 2px) and a slow flicker sit over the whole tube as the material of the monitor — these are the world, and the detector's "stripes" and "glow" findings are expected. Nothing has a drop shadow; the form panel is separated by a 1px rule and CRT-2 ground.

## Components

**Status bar cells** — flex cells 100% of bar height, `.9rem` horizontal padding, amber index digit; hover/focus/`aria-current` invert; active gets a trailing `*`.
**Download button (`.btn`)** — filled phosphor, CRT text, 600 uppercase label, arrow icon, `--glow`; hover → amber. The only filled element on the page; there is exactly one in the hero and one submit in the form.
**Alt-format links (`.dl-alt`)** — underlined phosphor, prefixed "also as … / …", ≥ 2rem hit height.
**File rows (`.file`)** — `-rw-r--r--  42K  Patrick_Padgett_Resume.pdf  ATS-safe, 2 pp.`; whole row is the link, ≥ 2.5rem tall; inverts on hover.
**Metrics (`.gauge`)** — VT323 number in amber, 600 uppercase caption, one-line description. No bars: the number is the fact.
**Job rows** — amber date column, 600 phosphor title with glow, Phosphor-70 org, `-` bulleted lines ≤ 78ch.
**Quotes** — recommendation text, attribution in label style.
**Form (`.mail`)** — mail-header strip (`To:` / `Subject:`), explicit `<label for>` on every field, `aria-describedby` to each error sentence, `:user-invalid` amber rule, errors shown after a submit attempt. The button says **Compose email** because that is what it does: the handler builds a `mailto:` draft; the note says so before and after. When a POST endpoint exists, rename the button and drop the mailto.
**Contact wires** — email, phone (`tel:+1` + 10 digits, never a masked string), LinkedIn, GitHub; icons are authored 24px SVG, one stroke weight; hit height ≥ 2rem.

## Motion

Sequence per section on first reveal: type the command (steps), then print the output. Display words print with `steps(8)` in 0.18s cadence. Reduced motion: all commands pre-typed, all output visible, smooth scroll off. Clock and uptime tick once a second; both are `aria-hidden`.

## Detector notes

The detector flattens `print.css` into the screen cascade, so it reports `#111111` print text against CRT backgrounds (false) and, without the print sheet, ~49 glow findings (the documented material). The `h1` wrapper is 16px because its two child spans carry the name and display sizes; "flat hierarchy" on it is structural. Sections open flush on a rule by design.

## Print

`print.css` is linked AFTER the inline screen stylesheet so its equal-specificity overrides win; the portrait resets `mix-blend-mode` to normal (screen-blend vanishes on white).

`print.css` (media="print") turns the session into a document: white ground, #111 text, no glow/scanlines/nav/form/typed commands, all output forced visible, links expose their URL, portrait grayscale. Roughly seven Letter pages; the PDF résumé remains the intended print artefact and is the first thing the page offers.

## Do's and Don'ts

**Do** keep every navigable label in plain English; keep the shell vocabulary in the `aria-hidden` command lines.
**Do** put name, role, proof, and the PDF button in the first viewport at 320, 390 and 1366.
**Do** honour the two phosphors; a new colour is a new monitor.
**Don't** show a percentage bar, spinner, or gauge for a number that isn't a percentage.
**Don't** let `overflow-x: hidden` stand in for a layout that fits.
**Don't** promise delivery the page can't perform — label the form by what it does.
**Don't** re-introduce the six-line fake login; two lines of banner is the ceiling.

## Critique #2 refinements
- Location/availability is its own amber line above the proof sentence; the proof sentence no longer carries geography.
- ≤30rem: banner drops its second line, display 3rem, tighter stack — name, role, location, proof and the PDF button fit 320×700 (button bottom 697).
- Experience is strict reverse chronology: Sprint (2001–2015) before CyberRazor (2005–2009).
- Form: `#form-status` `role="status"` live region carries the handoff message; the note's email anchor is never replaced.
- Nav scroller applies to 62rem (768 overflowed with no cue); focused cells scroll into view; focus-visible adds an inset amber bar to distinguish from `is-active`.
- Neither `html` nor `body` clips horizontal overflow — the layout fits at 320–1920.

## Critique #3 refinements
- Form fields are `.field` groups (label tight to its control, 1.35rem between fields); `#form-status` sits under the Compose email button.
- Nav end-cap `›` renders only when `.status ul` actually overflows (`is-overflowing`, set by JS on load/resize); focused cells centre in the scroller.
- Print hides the `ls` download listing and drops appended URLs on contact wires whose text is already the address.
- JSON-LD: `worksFor` = current (VimOps); past employers under `alumniOf`.

## Critique #4 refinements
- Tenure count is computed (`data-years-since="1996"`) so "years of production Linux" never drifts; source résumé still says "25 years" — reconcile in build_resume.py when next rebuilt.
- Required fields carry an amber `*` (aria-hidden; `required` does the accessible work); Role is marked optional; the mail header notes "* required".
- Handoff status includes its own mailto link, so recovery is one tap from the button.
- Print: `.quote` white with a hairline, ^G badge hidden, quote marks black.
- JSON-LD `alumniOf` merged into one array (education + past employers).

## Critique #5 refinements
- Footer no longer claims the formats "always agree"; the download is the document of record. Known gap: build_resume.py summary still says "25 years of production Linux" while the page computes 30 — fix the source ("Production Linux since 1996.") and regenerate PDF/DOCX/MD in /data/pat/resume-ats, then copy to assets/.
- Print `#` heading marks are black.

## Critique #6 refinements
- Mobile/tablet status bar is 44px (≤62rem) with `scroll-padding-top` 3.75rem; 320 stack tightened (display 2.85rem, header padding 1rem) so the PDF row still clears 700px (bottom 693).
