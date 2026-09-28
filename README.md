# work.patpadgett.com — The Session

Web résumé for Patrick Padgett, rendered as a login session on a green-phosphor UNIX
terminal. Flat HTML, CSS and JS in one file; no build step, no CDNs, self-hosted fonts.
Live at https://work.patpadgett.com/ (GitHub Pages, CNAME in this repo).

Positioning (2026-09-28): DevOps and Cloud Engineer. Kubernetes, Terraform, Ansible and
CI/CD across AWS, Azure and GCP, backed by twenty-five years of production ownership.
Telecom billing mediation remains in the Sprint record but is no longer the headline.

## Files

    index.html                  the page (CSS and JS inlined); edit directly
    print.css                   media="print" sheet: the session as a white document
    fonts.css                   @font-face reference copy (the same block is inlined in index.html)
    404.html, robots.txt, sitemap.xml, CNAME, favicon.ico
    PRODUCT.md                  product truth (Impeccable)
    DESIGN.md                   visual system + per-critique refinement log
    .impeccable/                surface brief, critiques, detector output, review screenshots
    assets/
      Patrick_Padgett_Resume.pdf / .docx / .md    the downloadable résumé (see Content provenance)
      avatar.jpg, avatar@2x.jpg                   headshot, supplied by Patrick
      favicon.svg, icon-512.png, apple-touch-icon.png
      fonts/*.woff2                               VT323, IBM Plex Mono (OFL)

## Content provenance

- Résumé files: copies of /data/pat/career/resume/tailored/_base/Patrick_Padgett_Resume_DevOps.{pdf,docx,md},
  which build_from_master.py generates from /data/pat/career/MASTER_RESUME.md. Never hand-edit
  them here; fix the master, rebuild, copy the three files in, and update the byte sizes shown in
  the two `ls -lh` listings (currently 47K / 40K / 7K).
- Page bullets (About, Experience, Skills, Corkscrew, Education): copied verbatim from that DevOps
  build, same order. CyberRazor and the 1996–2001 ISP line come from MASTER_RESUME.md because they
  are on the page's timeline even though the two-page résumé drops them.
- Hero metrics: ~112 plants on Kubernetes (Jabil), −70% deployment time (VimOps), 99.999% uptime for
  14 years (Sprint). All three are résumé bullets; nothing on the page is a number the résumé lacks.
- Recommendations: verbatim, from MASTER_RESUME.md "Recommendations and Press".
- Field notes: eleven posts from /data/pat/websites/blog/posts chosen for DevOps/ops relevance
  (titles and one-line summaries from their frontmatter). Links point at
  https://blog.patpadgett.com/posts/<slug>/ and dates match the blog's (back-dated 2026-01-30..
  2026-09-28 on 2026-09-28; see websites/blog/build/redate-2026-09-28.json). All eleven are live.
  To add a row for a not-yet-published post, give the <li> class "note is-queued" and a
  <span class="note-title" data-href="..."> instead of the <a>; inline JS turns it into a link at
  13:00 New York on its date (the blog's publish hour). If a post's date or slug changes in the
  blog source, update the row here.
- The earlier generator (/data/pat/resume-ats/build_site.py, build_resume.py) no longer produces
  this page; do not run it over this repo.

## The design

Every section is a shell command and its output. The status line across the top is a tmux/screen
bar with numbered windows, a clock (≥78rem) and the PDF cell. Sections:

    finger pat                 hero: name, DEVOPS / & CLOUD / ENGINEER, portrait as a framebuffer
                               dump, three headline numbers
    ls -lh ~/resume/           the three résumé files with real byte sizes
    cat README; uptime         summary + tenure counters
    last -x pat | sort -r      work history
    ls -l /usr/local/bin/      skills, ten rows mirroring the résumé categories
    tail -n 11 ~/notes/ops.log field notes: blog posts about the work behind the bullets
    wall < /var/mail/pat       the four verbatim recommendations
    man corkscrew              the open-source project as a man page
    finger -l pat | tail       education
    mail -s 'job' pat@...      contact form (mailto handoff until a POST endpoint exists)
    logout                     footer

Palette: CRT black #060907, P1 phosphor green #3dff73 (with dimmer steps), P3 amber #ffb000 for
commands, dates and numbers, body text #c9f7d3. Type: VT323 for display, IBM Plex Mono for
everything else. Full token set in DESIGN.md.

## Animation

- Power-on: the whole page opens like a CRT warming up (vertical line -> full raster), 1.1 s.
- Persistent: scanlines + vignette overlay, a slow refresh band sweeping down every 9 s, a blinking
  block cursor after every prompt, the framebuffer portrait flickers once every 7 s.
- Per section, on scroll-in: the command is typed character by character (28-74 ms/char), then the
  output lines print top to bottom (55 ms apart) with a left-to-right stepped wipe.
- Hero: the three title lines print with a stepped wipe.
- Quotes print in as they enter the viewport.
- Live: clock in the status line; uptime counter in the banner counts seconds since 1996-09-01.
- Hover: file rows, note rows and status-line windows invert or tint; the submit button goes amber.
- Easter egg: type "amber" anywhere on the page to swap the tube to an amber P3 monitor.
- prefers-reduced-motion: everything renders visible immediately, nothing moves, cursor hidden.

## QA performed (2026-09-28)

Playwright (Chromium, --no-sandbox) at 1440×900, 820×1180, 390×844 and 320×700, reduced motion:
- zero console errors, no horizontal overflow at any width (only the nav's own scroller exceeds
  the viewport, by design, with the amber › end-cap when it does).
- First viewport: name, three display lines, location, proof sentence and the PDF button fit at
  320×700 (button bottom 622px; Word/Markdown row bottom 658px).
- Nav measured at 820–1440: end-cap appears wherever cells overflow (≤~1090px), clock only ≥1248px.
- Print emulation to Letter: 10 pages, field notes print as title + URL.
- Impeccable detector: remaining findings are the documented CRT material (glow, scanlines) and
  print.css colours flattened into the screen cascade; see DESIGN.md "Detector notes".
- Screenshots in .impeccable/review/.

## Before this goes live / known gaps

- Contact form hands off to a mailto: draft; wire a POST endpoint and rename the button when one exists.
- Field-notes dates are copied from the blog source; a re-dated or re-slugged post there needs a
  matching edit here.
- Hotjar snippet (6780883) is in the head of index.html and 404.html.

## Deploy

    git add -A && git commit -m "..." && git push origin main

GitHub Pages serves the repo root.
