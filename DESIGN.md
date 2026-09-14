---
name: patpadgett.com — The Press Sheet
description: A résumé printed as the offset-litho press proof of itself; CMYK process inks on bright white, marks that do layout work.
colors:
  bright-white: "#ffffff"
  key-black: "#111111"
  key-70: "#4d4d4d"
  key-40: "#9a9a9a"
  key-10: "#e9e9e9"
  process-cyan: "#0099d8"
  process-magenta: "#ec008c"
  magenta-solid: "#c4006f"
  process-yellow: "#fff100"
typography:
  display:
    fontFamily: "Big Shoulders Display, Arial Narrow, sans-serif"
    fontSize: "clamp(3.2rem, 10.5vw, 8rem)"
    fontWeight: 900
    lineHeight: 0.86
    letterSpacing: "-0.01em"
  headline:
    fontFamily: "Big Shoulders Display, Arial Narrow, sans-serif"
    fontSize: "clamp(2.6rem, 6vw, 4.75rem)"
    fontWeight: 900
    lineHeight: 0.9
  title:
    fontFamily: "Public Sans, system-ui, sans-serif"
    fontSize: "1.25rem"
    fontWeight: 700
    lineHeight: 1.3
  body:
    fontFamily: "Public Sans, system-ui, sans-serif"
    fontSize: "1.0625rem"
    fontWeight: 400
    lineHeight: 1.55
  label:
    fontFamily: "Azeret Mono, ui-monospace, monospace"
    fontSize: "0.8rem"
    fontWeight: 600
    letterSpacing: "0.06em"
rounded:
  none: "0"
spacing:
  bar: "32px"
  gutter: "clamp(1.25rem, 5vw, 4.5rem)"
  section: "clamp(3.5rem, 9vw, 7.5rem)"
  row: "0.9rem"
components:
  stamp:
    backgroundColor: "transparent"
    textColor: "{colors.key-black}"
    typography: "{typography.label}"
    rounded: "{rounded.none}"
    padding: "0.7rem 1rem 0.65rem 0.85rem"
  stamp-primary:
    backgroundColor: "transparent"
    textColor: "{colors.process-yellow}"
    typography: "{typography.label}"
    rounded: "{rounded.none}"
    padding: "0.9rem 1.25rem"
  colorbar-cell:
    typography: "{typography.label}"
    height: "{spacing.bar}"
    rounded: "{rounded.none}"
  input:
    backgroundColor: "transparent"
    textColor: "{colors.bright-white}"
    typography: "{typography.body}"
    rounded: "{rounded.none}"
    padding: "0.55rem 0"
---

# Design System: patpadgett.com — The Press Sheet

## Overview

**Creative North Star: "The Press Sheet"**

The site is a single sheet of bright white coated stock coming off an offset press, and every piece of print furniture does a job. The color-control bar across the top is the navigation. Crop marks frame the trim. Registration targets carry the headline numbers. Downloads are job-ticket stamps whose cyan and magenta plates slip out of register on hover. Whole sections print as solid process-ink fields (cyan, yellow, magenta, K) rather than as accents on white, and every fact on the sheet stays K black or white so no claim competes with chrome.

Density alternates: a poster-scale hero, then dense record rows, then a wide magenta spread of quotes, then a quiet white column pair, ending on a K field with the form. The rhythm is one hairline rule system throughout; there are no cards, no shadows, no rounded corners.

**Key Characteristics:**
- Strictly CMYK plus white; no tints, gradients, or off-palette grays beyond the K ramp.
- Condensed 900-weight caps for anything that must be read from across the room; mono for anything a pressman would write on the ticket.
- Hairline rules (1px, 2px for section tops) are the only container language.
- Motion is one press stroke: a stepped clip-path wipe, never a fade.

## Colors

Process inks on white; color commits at field scale, facts stay achromatic.

### Primary
- **Process Cyan** (#0099d8): Proof section ground, TELECOM headline word, first registration target, nav cell. Darkened from press-standard #00AEEF because pure process cyan on white reads at ~2.4:1; #0099d8 reaches 3.2:1 for display sizes.
- **Process Magenta** (#ec008c): BILLING headline word, second registration target, nav cell, hover misregistration on stamps.
- **Magenta Solid** (#c4006f): the Signed-off section ground. Darker than the ink so white body text passes 5.9:1.
- **Process Yellow** (#fff100): Inks section ground, MEDIATION headline word (knocked out of a K bar, never on white), the PDF nav cell, the primary submit stamp on K, selection highlight, form caret.

### Neutral
- **Bright White** (#ffffff): the stock. Page ground and text on K/magenta fields.
- **Key Black** (#111111): all body text, rules, crop marks, ENGINEER, the Job-ticket field.
- **Key 70** (#4d4d4d): secondary captions and org names on white and yellow (7.5:1).
- **Key 40** (#9a9a9a): Corkscrew nav cell, dashed contact rule, link underline tint.
- **Key 10** (#e9e9e9): reserved; currently unused on the shipped page.

### Named Rules
**The K-Only Facts Rule.** Numbers, dates, claims, quotes and body copy print in Key Black or white. Color belongs to fields, marks, bars and headline words, never to a fact.

**The No Yellow-on-White Rule.** Process yellow never sits on the white stock. It prints on K, or K prints on it.

## Typography

**Display Font:** Big Shoulders Display 900 (with Arial Narrow fallback)
**Body Font:** Public Sans 400/500/700 (with system-ui fallback)
**Label/Mono Font:** Azeret Mono 400/600

**Character:** A poster grotesk built for one-word lines, a plain federal-issue sans for the record, and a mono that reads like a job ticket. Each face has exactly one job.

### Hierarchy
- **Display** (900, clamp(3.2rem, 10.5vw, 8rem), 0.86): the four stacked hero words, one per ink. Uppercase.
- **Headline** (900, clamp(2.6rem, 6vw, 4.75rem), 0.9): section h2s, uppercase, `text-wrap: balance`. Registration-target numbers use the same face at clamp(2.4rem, 4vw, 3.4rem).
- **Title** (700, 1.25rem, 1.3): job titles in the record; org name follows in 400 Key 70 after a middle dot.
- **Body** (400, 1.0625rem, 1.55): measure capped at 76ch; the lede is 500 at clamp(1.2rem, 1.9vw, 1.55rem) and 42ch.
- **Label** (600, 0.8rem, 0.06em, uppercase): ticket strip, plate captions, dates, skill keys, stamp text, form labels, colophon.

### Named Rules
**The One-Word Line Rule.** Display type sets one word per line, each word one ink, leading 0.86. It never sets a sentence.

**The Ticket Mono Rule.** Mono is for what a pressman writes: job numbers, plate captions, dates, file formats, field labels. Never for body copy or emphasis.

## Layout

One sheet, full bleed. A 32px fixed color bar (28px under 640px) sits above everything; body padding compensates. Content lives inside a 1180px max container with a fluid gutter of clamp(1.25rem, 5vw, 4.5rem); the container has no padding of its own, the section carries it. Sections pad clamp(3.5rem, 9vw, 7.5rem) vertically.

The hero is a 3:2 grid: display stack left, portrait plate above three registration targets right, aligned to the bottom edge; below 900px it stacks portrait, words, targets. The files bar is a two-column grid (label, stamps) with the contact wires on a dashed rule beneath. Record rows and skill rows are 9.5rem/11rem label columns plus a fluid column, collapsing to one column at 720px. Quotes are an auto-fit grid (min 24rem) with dense flow; the last quote spans full width at ≥48rem. Two-column sections use auto-fit at min 22rem.

Crop marks are fixed at the four trim corners (bottom pair hidden under 640px). Spacing rhythm: 0.9rem row padding, 1rem between targets, more space above a heading than below it.

## Elevation & Depth

No shadows anywhere. The page is a flat printed sheet; depth is conveyed only by ink fields changing behind the content and by the misregistration effect on hover, where two offset plate outlines in cyan and magenta multiply over the stamp (screen blend on the K field).

### Named Rules
**The Flat Sheet Rule.** Nothing casts a shadow, nothing blurs, nothing is glass. If it needs separation, rule it.

## Shapes

Zero radius on every element, including inputs and buttons. Borders are 1px hairlines (`--stroke`), 2px for section-opening rules, stamp borders and form underlines. Bullets in the record are 0.5rem hairline dashes. Registration targets are circle-and-crosshair SVGs with two filled opposite quadrants. Icons are 1.6px stroke, square caps, miter joins, 24px grid.

## Components

### Buttons (stamps)
- **Shape:** rectangular, 2px border in currentColor, zero radius.
- **Primary (`.stamp`):** transparent ground, inherits text color; mono 1.05rem format code with 0.7rem sub-caption; file icon spans both rows.
- **Hover / Focus:** cyan pseudo-plate slips (-3px, -2px) and magenta plate slips (3px, 2px) in three steps over 320ms; focus ring 3px magenta (yellow on the magenta field). Active nudges 1px.
- **Submit (`.stamp-btn`):** yellow border and text on the K field, single-row with arrow icon, padding 0.9rem 1.25rem; stretches full width under 560px.

### Colorbar cells (navigation)
- **Style:** fixed 32px bar, each cell a flat process-ink or K-ramp block with mono 0.7rem uppercase label; PP home cell white at far left, PDF cell yellow with 2px K left rule at far right.
- **States:** hover and `aria-current` paint a 4px bar along the cell bottom (K on light cells, yellow on K cells). Labels collapse to color-only under 560px.

### Inputs / Fields
- **Style:** transparent, white text, 2px white bottom rule only, no radius, yellow caret.
- **Focus:** rule turns yellow with a 2px yellow box-shadow underline.
- **Error:** `:user-invalid` turns the rule magenta; after a submit attempt an inline `.err` sentence appears under the field in pale pink (#ffd1e8).

### Registration targets
- **Style:** 3.25rem SVG target inked cyan, magenta, K in sequence; display number beside it, mono label, Key 70 caption; each row opens with a hairline rule.

### Record rows
- **Style:** 2px K rule opens the list; each job is a hairline-ruled row with mono 600 date column and title/org/bullets column.

### Quotes
- **Style:** 2px white rule on the magenta-solid field, 500-weight quote at clamp(1.2rem, 1.7vw, 1.45rem), mono uppercase name and sans role beneath.

## Do's and Don'ts

### Do:
- **Do** print sections as solid ink fields (cyan, yellow, magenta-solid, K) with white or K text; a new section picks the next ink in the CMYK sequence.
- **Do** open every list or table with a 2px K rule and separate rows with 1px hairlines.
- **Do** set every date range with an en dash and no-break spaces (2001–2015); keep the ASCII hyphen only in the résumé source files.
- **Do** keep motion to the press stroke: `steps()` easing, clip-path wipe, visible default, gated behind `prefers-reduced-motion: no-preference` and the `.js` class.
- **Do** self-host fonts from assets/fonts and keep the three-face system: one display, one body, one mono.

### Don't:
- **Don't** put process yellow on the white stock or any gray tint between Key 70 and white for text.
- **Don't** add cards, shadows, radii, gradients, glass, or icon tiles; the sheet is flat and ruled.
- **Don't** set display type in more than one word per line or below 900 weight.
- **Don't** use mono for body copy or emphasis; it is ticket writing only.
- **Don't** introduce a color outside CMYK + white; a fifth ink is a new job.
