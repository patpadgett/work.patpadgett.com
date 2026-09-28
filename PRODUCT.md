# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

Confirmed: flat static HTML/CSS/JS with no build step and no runtime frameworks or CDNs, matching Patrick's standing convention for every patpadgett.com build (self-hosted or system fonts; a Google Fonts link is acceptable).

## Users

Confirmed: two equally weighted readers.

1. Recruiters and ATS-driven screeners hiring for DevOps / Cloud / platform / SRE roles (and, secondarily, telecom billing mediation). They arrive from a job application, LinkedIn, or a cold email, skim for seconds, and need the fit signal and the downloadable résumé fast.
2. Hiring managers reading closely after a referral or cold email. They want proof: Kubernetes across ~112 plants at Jabil, the Ansible/Jenkins releases at Raymond James, fourteen years at five nines at Sprint, the open-source track record, the blog posts that show how he thinks about production, and the people who vouched for him.

Secondary (inferred from the landing-page role): anyone who lands on patpadgett.com and wants to know who Patrick is and how to reach him.

## Product Purpose

A web résumé page for Patrick Padgett that serves as the patpadgett.com landing page, fed by the same source data as the ATS résumé (/data/pat/resume-ats/build_resume.py) and linking to the downloadable PDF, DOCX, and Markdown résumé files. Success: a reader understands within one viewport that Patrick is a senior DevOps and Cloud Engineer with two decades of production ownership behind him, finds the proof, downloads the résumé in the format they need, and contacts him.

Confirmed: this page IS the patpadgett.com homepage.

## Positioning

DevOps and Cloud Engineer (decided 2026-09-28; supersedes the telecom-first positioning). Kubernetes, Terraform, Ansible and CI/CD across AWS, Azure and GCP: containerized Jabil's iFactory onto Kubernetes across ~112 plants, automated Raymond James releases with Ansible and Jenkins, and ran Sprint's 50-server billing mediation estate at 99.999% for 14 years as the on-call Tier 3 owner. The claim is production ownership: someone who has carried the pager for systems that cannot go down and builds them the modern way. Twenty-five years of production Linux. Author of corkscrew (2000), packaged in Debian, Ubuntu, Red Hat, CentOS, FreeBSD and GNU Guix.

## Operating Context

- Content source of record: /data/pat/career/MASTER_RESUME.md → build_from_master.py → career/resume/tailored/_base/Patrick_Padgett_Resume_DevOps.{pdf,docx,md}. The page's bullets are copied from that DevOps build; the three files are copied into assets/ as Patrick_Padgett_Resume.{pdf,docx,md}. (build_resume.py / build_site.py in resume-ats are the earlier generator and no longer produce this page.)
- Field notes: /data/pat/websites/blog/posts (published daily to blog.patpadgett.com by cron; a post goes live at ~13:00 New York on its date).
- Extended, verified content (recommendations, links, music, skills detail): /data/pat/patpadgett-variants-2026-09/CONTENT-BRIEF.md (verified 2026-09-05).
- Prior patpadgett.com builds exist and count as anti-reference for visual identity: /data/pat/patpadgett-variants-2026-09 (five skill variants), /data/pat/patpadgett-hallmark (light paper, cobalt, Space Grotesk/Inter), /data/pat/patpadgett-linkedin-site (dark graphite, Archivo, oxide red).
- Readers arrive from job applications, LinkedIn (linkedin.com/in/patpadgett), GitHub (github.com/patpadgett), cake.me/patpadgett, and cold emails.
- Patrick is actively job-searching from the Greater Tampa Bay, FL area; open to remote, hybrid, contract, and full-time.

## Capabilities and Constraints

Confirmed:
- Freeform design: Patrick placed no layout, length, or ATS-parsing constraint on the web page. ATS constraints apply only to the downloadable files, which already exist.
- Must link to the downloadable résumé files: Patrick_Padgett_Resume.pdf, .docx, .md.
- Content claims (numbers, employers, dates) come only from the source data and CONTENT-BRIEF.md; nothing invented.
- Exclusions: Hindia Indonesia Travel Agency stays off. No expired notary credential.

Standing conventions (from Patrick's prior site work; treat as binding unless he says otherwise):
- Responsive 320 to 1440, no horizontal scroll, one h1, alt on every image, prefers-reduced-motion respected, zero console errors.
- Client-ready copy only; zero meta or internal language on the page.
- Contact form markup is real and POST-ready with action="#" and a visible note to email directly until wired; CTA labels are action-oriented.
- Deliver a README.md: design decisions, content provenance, QA performed, "before this goes live" list.

Undecided:
- Deploy target / host.

## Brand Commitments

- Name: Patrick Padgett, goes by Pat. Handle everywhere: patpadgett.
- Headline on the published résumé: "DevOps and Cloud Engineer | Kubernetes, Terraform, Ansible, CI/CD." Tagline on file: "Code Artist, DevOps Maven: Refined Exactitude."
- Voice: direct, concrete, dryly funny where it fits; never salesy. The corkscrew README self-description ("My name is Pat Padgett. I'm a dork.") is on-brand and quotable via the Linux Magazine review.
- No pinned palette, typeface, or aesthetic. The only visual constraint is negative: visibly different from the hallmark and linkedin-site builds.

## Evidence on Hand

- Headline numbers (Sprint, 2001-2015): $2M saved via the EDR routing application; +250% mediation throughput via parallel processing; -50% alarm time-to-resolution via ELK.
- Verbatim recommendations with exact attribution in CONTENT-BRIEF.md: Kathryn Walker (Chief Network Officer, Sprint), Renee Keffer (Director Network Operations, Sprint), Jake Weaver (Founder & CEO, codesigned), Charly Kühnast (Linux Magazine, Sept 2014).
- corkscrew: github.com/patpadgett/corkscrew, 192 stars at last check, Wikipedia article, Debian man page, reviewed in Linux Magazine and 2600.
- Résumé files: career/resume/tailored/_base/Patrick_Padgett_Resume_DevOps.{pdf,docx,md}, copied to assets/Patrick_Padgett_Resume.{pdf,docx,md}.
- Headshot: /data/pat/resume-ats/final/assets/avatar.jpg and avatar@2x.jpg (confirmed; Patrick supplied it for use on the page).
- Education: Certificate, Graphic Arts, Lake Career & Technical Center, Camdenton MO, 1996-98; 2nd place State of Missouri VICA, offset lithography.
- Absent, do not fabricate: client logos, case studies with named clients, pricing, additional testimonials, current employer.

## Product Principles

1. Proof before adjectives. Every claim on the page traces to the source data; numbers and quoted recommendations carry the persuasion.
2. Two readers, one page. The ten-second skimmer and the close reader both leave satisfied; the skim path lands on fit, numbers, and download, the deep path gets the full record.
3. The downloads are the conversion. PDF, DOCX and Markdown are always one obvious action away.
4. Single source of truth. The page's bullets are the DevOps résumé's bullets; if it drifts from the files in assets/ it is wrong.
5. Distinct from its predecessors. Each patpadgett.com build is a new world, not a recolor of the last one.

## Accessibility & Inclusion

Standing requirements: semantic single-h1 structure, alt text on all images, keyboard-reachable controls, prefers-reduced-motion honored, readable contrast. Patrick has mobility limitations; nothing on the page may depend on precise pointer gestures. No further product-specific standard was established.
