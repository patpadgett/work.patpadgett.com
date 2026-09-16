---
version: 1
slug: "index-html"
primary_target: "index.html"
related_targets: []
---

# Surface: index.html (patpadgett.com homepage)

Scope: the homepage résumé page. Visitor mode: Persuade.
Audience: recruiters/ATS screeners skimming (telecom billing mediation, DevOps) and hiring managers reading closely; equal weight.
Job: know within one viewport who Patrick is and that he fits; find proof; download PDF/DOCX/MD; contact.
Proof: $2M / +250% / -50% Sprint numbers; four verbatim recommendations; corkscrew packaging record; full role history from build_resume.py.
Constraints: flat HTML/CSS/JS, no build step, no runtime CDNs; content only from build_resume.py + CONTENT-BRIEF.md; Hindia off; one h1; alt on all images; reduced-motion honored; 320-1440 no horizontal scroll; README.md delivered.
Unresolved: deploy host.

## Direction contract

THESIS: A résumé read off a green-phosphor terminal. The shell is where the work has always happened; the record is what the shell prints. Owner decision (critique #1, 2026-09-16): keep the terminal. The earlier "Press Sheet" (offset-litho) contract was never shipped and is retired.

OWN-WORLD: Near-black CRT #060907; P1 phosphor green #3dff73 for the machine and the record, P3 amber #ffb000 for the operator's emphasis (metrics, dates, the typed command, the PDF cell); green-white #c9f7d3 body. VT323 for the four-word role, h2s and metrics; IBM Plex Mono for everything read closely. Glow, scanlines and a slow flicker are the monitor. Real shell commands (`finger pat`, `ls -lh ~/resume/`, `last`, `wall`, `man corkscrew`, `mail`) sit aria-hidden above each section; the labels a reader navigates by are plain English.

STORY: "This man ran carrier billing pipelines for 14 years and builds them the modern way; here are the numbers, here is who vouches, here is the file."

FIRST VIEWPORT (every width, 320 up): two-line banner (host, uptime), the `finger pat` prompt, name at 600 weight, TELECOM / BILLING / MEDIATION / ENGINEER one word per line, amber location + availability line, one Sprint/Jabil/Raymond James proof sentence, filled DOWNLOAD RÉSUMÉ (PDF) with Word / Markdown beside it. Desktop adds the framebuffer portrait and the three metrics in the right column.

FORM: The mail composer builds a mailto: draft and says so ("Compose email"); explicit labels, live status beside the button, fallback address always present. Becomes a real POST when an endpoint exists.

FINISH: print.css turns the session into a document (white, document head with grayscale portrait, no nav/form/commands/download furniture). Critique trend 14 → 25 → 28.
