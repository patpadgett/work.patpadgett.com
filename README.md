# patpadgett.com — The Session

Homepage / web résumé for Patrick Padgett, rendered as a login session on a green-phosphor
UNIX terminal. Flat HTML, CSS and JS in one file; no build step at runtime, no CDNs.

## Files

    final/
      index.html                  the page (CSS and JS inlined)
      PRODUCT.md                  product truth (Impeccable init record; predates the terminal redesign)
      DESIGN.md                   visual system (written for the earlier "Press Sheet" version; see below)
      README.md                   this file
      fonts.css                   @font-face block inlined by build_site.py (keep; build input)
      assets/
        Patrick_Padgett_Resume.pdf / .docx / .md   downloadable résumé (ATS-safe outputs)
        avatar.jpg, avatar@2x.jpg                  headshot, supplied by Patrick
        favicon.svg
        fonts/*.woff2                              self-hosted (VT323, IBM Plex Mono; OFL)
    build_resume.py               single source of truth for résumé content (R dict) -> PDF/DOCX/MD
    build_site.py                 renders index.html from the same R dict
    site.css, site.js             sources inlined into index.html by build_site.py

Rebuild everything:

    cd /data/pat/resume-ats
    python3 build_resume.py     # résumé files -> final/assets/
    python3 build_site.py       # index.html

Deploy: upload the contents of `final/` (minus `.impeccable/`) to the web root. Relative paths only.

## The design

Every section is a shell command and its output. The status line across the top is a tmux/screen
bar with numbered windows (1 README, 2 last, 3 bin, 4 wall, 5 man, 6 mail), a live clock and the
PDF. Sections:

    finger pat                 hero: name, title, portrait as a framebuffer dump, three headline
                               results as ASCII progress bars
    ls -lh ~/resume/           the three résumé files with real byte sizes
    cat README; uptime         summary + tenure counters
    last -x pat | sort -r      work history
    ls -l /usr/local/bin/      skills
    wall < /var/mail/pat       the four verbatim recommendations
    man corkscrew              the open-source project as a man page
    finger -l pat | tail       education (Camdenton lithography lives here as .plan)
    mail -s 'job' pat@...      contact form
    logout                     footer

Palette: CRT black #060907, P1 phosphor green #3dff73 (with dimmer steps), P3 amber #ffb000 for
commands and numbers, body text #c9f7d3. Type: VT323 for display, IBM Plex Mono for everything else.

## Animation

- Power-on: the whole page opens like a CRT warming up (vertical line -> full raster), 1.1 s.
- Persistent: scanlines + vignette overlay, a slow refresh band sweeping down every 9 s, a blinking
  block cursor after every prompt, the framebuffer portrait flickers once every 7 s.
- Per section, on scroll-in: the command is typed character by character (28-74 ms/char), then the
  output lines print top to bottom (55 ms apart) with a left-to-right stepped wipe.
- Hero: the four title words print with a stepped wipe; the three progress bars fill to their value.
- Quotes print in as they enter the viewport.
- Live: clock in the status line; uptime counter in the banner counts seconds since 1996-09-01.
- Hover: file rows and status-line windows invert to solid green; the submit button goes amber.
- Easter egg: type "amber" anywhere on the page to swap the tube to an amber P3 monitor.
- prefers-reduced-motion: everything renders visible immediately, nothing moves, cursor hidden.

## QA done

Playwright (Chromium, --no-sandbox) at 1440, 820 and 390: no horizontal overflow, all .out blocks
reveal, hover/focus/invalid states verified live, amber toggle works, reduced-motion path shows all
content. Screenshots in .impeccable/review/.

## Known gaps

- Contact form is not wired to a backend; on submit it validates, then hands off to a mailto: link.
- DESIGN.md still documents the previous Press Sheet system; this README is the current reference.
