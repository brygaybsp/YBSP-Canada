# YBSP Canada website: collaboration guide

This file is the project knowledge base for anyone (human or agent) working on this site. It records how the site is built, the standing rules, the findings already proven wrong, and how work flows. Read it before starting any task. If it conflicts with an outside audit or draft, this file wins.

## Site architecture

- Static website. Hand-written HTML, CSS, and JavaScript. No CMS, no backend, no database, no build framework.
- Ten root pages (index, about, programs, events, news, news-single, donate, contact, get-involved, careers) and eight team profile pages under /team/.
- All content is inline in the HTML files, including the bilingual dictionaries. Each file carries an inline `const translations = {` object with EN and FR blocks. Language is chosen client-side by URL path (/fr/ wins, then ?lang=, then localStorage).
- French URLs are Netlify rewrites in netlify.toml (status 200, URL stays French): /fr/ serves index, /fr/a-propos serves about, /fr/programmes serves programs, /fr/impliquez-vous serves get-involved, /fr/evenements serves events, /fr/nouvelles serves news, /fr/nouvelle serves news-single, /fr/carrieres serves careers, /fr/contact, /fr/faire-un-don, /fr/equipe/* maps to /team/:splat.
- Source: GitHub repository brygaybsp/YBSP-Canada. Hosting: Netlify (ybspcanada.org). Netlify deploys on every push to main and charges build credits per commit, so batch small fixes into one PR and one commit where possible.
- Forms: 8 Netlify Forms. get-involved has the main volunteer form (Netlify "volunteer-application") and a two-field alert form (Netlify "volunteer-alert-list"). Careers, contact, events (proposal plus registration modal), and news (newsletter with a visible email label and a required CASL consent checkbox) have their own forms. Form email notifications go to info@ybspcanada.org.
- Donations: Zeffy is live and the donate page links to the Zeffy form "Donate to Change Lives" plus Interac e-Transfer (donations@ybspcanada.org). The page states donations do not currently generate charitable tax receipts (CRA registration in progress).

## Standing rules

- Validate HTML tag balance programmatically for every commit. Every team-member-card div closed before the next begins.
- Never alter other members' working photo paths or initials avatars. Never swap a photo without Leis's explicit say-so for that person.
- Never wire form handlers with inline onsubmit. The live site serves inline onsubmit attributes mangled (single quotes with backslash escapes), so inline handlers throw on submit and forms post natively to Netlify's generic thank-you page. Wire handlers with addEventListener inside a script block.
- Bilingual equal weight: every changed string has both an EN and an FR value. French is never a smaller footnote. In events.html the i18n dict mixes unquoted keys and double-quoted keys; match each entry's existing key style when editing. In events.html the dict title values use HTML-escaped &amp;, not raw &; other files vary, check the actual bytes before editing.
- WCAG AA: 4.5:1 text contrast, 3:1 large text and UI, one h1 per page, no skipped heading levels, semantic landmarks plus skip link, visible focus, prefers-reduced-motion respected, meaningful alt text, labeled inputs, 24px touch targets.
- No invented claims, numbers, or quotes. Every number, date, name, and claim in a change must be checked against its primary source (the repo, the live site, or Leis's confirmed words) before the PR is proposed.
- No credentials in the repo, in prompts, or in shared files. No Google Workspace, Ads, Zeffy, Desjardins, or Google Ads API access for implementation work. GitHub access is repo-scoped to brygaybsp/YBSP-Canada only.
- Main is never edited directly. Do not merge. Do not publish. Only Leis merges, on his explicit "Merge."
- No PR or live site change without showing Leis first.
- Keep feature branches after merge.
- Batch small fixes into one PR. Netlify builds per commit; a root-plus-team change must not land as two commits if one will do.

## Brand and content rules

- All public visuals feature Black youth, reflecting the organization's Black-led identity. Programs serve everyone.
- Never publicly describe YBSP Canada as Black-led, Black-serving, or Black-mandated. Black-led and Black-youth language belongs only in grant documents where the funder requires it.
- Never mention the 2014 $10,000 Coca-Cola grant in public content.
- Never use the "From Bujumbura to Gatineau" origin concept.
- No public posts about future projects with no funding on hand. No MARP content on the site until funded.
- Projects are in Ottawa-Gatineau, not only Gatineau.
- Burundi photos are labeled as Burundi archives, never as Canada programs.
- The site's Burundi chapter: the movement began in 2011 and was chartered in 2013. Use "2011 Movement • 2013 Charter" / "Mouvement 2011 • Charte 2013" for the About badge. Do not write "Founded in 2011" alone.
- Unverified scale claims (150 youth, 80 volunteers, cohort numbers) were confirmed not real on November 6, 2026 and were relabeled as planned. Do not present any program as running, funded, or completed unless the verified record says so.

## Do not re-report (verified wrong)

These findings from third-party audits were checked against the repo and the live site and proven wrong. Do not file them, fix them, or mention them as open issues.

- Homepage counters (repo has data-target="15"/15+ and "100"/100%).
- A /privacy route (no such page; all footers link to the Privacy Policy PDF).
- Heading hierarchy (exactly one h1 per file).
- "5 truncated French alts" (complete sentences).
- Get Involved skip link, privacy link, or social icons missing (all present).
- #working-groups anchor missing (exists).
- Contact "Email Address *" as a wrong label (correct required-field label).
- A Nader profile page (does not exist).
- The "Ministerial Ordinance No. 530/1281" quote (does not exist anywhere in the repo).
- Hashtag #Sororalkaye (zero occurrences repo-wide; all are #SororaIkaye).
- Article id=5 "rigorous financial accounting / voluntary solidarity transfers" sentence (does not exist; the article is already conditional).
- FR nav_mission as wrong (index FR is "Mission & Mandat", correct).
- The "©2026Youth" missing space (text-extraction artifact; the space is present in repo source and live served bytes).

## Current state (November 14, 2026)

- Latest Gemini audit (#4, November 6, 2026) scored 96/100. No Critical, High, or Medium findings remain.
- PR #66 merged November 14, 2026: the three parked Low polish items (news article 6 combined tag, About Burundi badge, homepage supporters aria-label). Issue #65 closed. No parked audit items remain.
- PR #67 merged November 14, 2026: removed two unused Faustin photo files (images/faustin-nimbona.JPG and images/faustin-nimbona.jpg) that collided on Windows (case-insensitive filesystem) and caused a phantom change in GitHub Desktop. The live photo is images/faustin-nimbona-2026.jpg. Do not re-add the deleted files.
- Mobile 375px rendering is a standing gap: it has never been verified in the weekly audits. Desktop rendering is verified at 1024/1200px.
- News latest article is August 28, 2026. News cadence is an owner judgment call, not a defect.
- Orphan files: two unlinked FR PDFs in docs/ (YBSP_Canada_Financial_Transparency_Statement_FR.pdf and YBSP_Canada_Fiche_Information.pdf) and an orphaned 'community-action' entry in the events albumData. Known, not filed.
- Weekly site audit runs on a schedule and its ledger lives outside this repo. The audit verdicts, not this file, are the record of what was checked each week.

## Roles

- Muse: primary webmaster, knowledge manager, validator, coordinator. Owns what is true (the verified record), what is allowed (brand, bilingual, accessibility, funder rules), and whether a change is safe to recommend for merge. Writes every assignment. Reviews every implementation. Is the only agent that recommends a merge to Leis.
- Implementation partner (Antigravity or Muse via the GitHub API): owns code changes on feature branches, local validation, browser and mobile testing, and a clean PR with a completion report. Does not decide content truth, funder alignment, or whether a change ships. Does not merge and does not touch production directly.
- Leis: owner and only merger. Approves every merge with his explicit "Merge." Approves any spend, any account change, and any public-facing organizational statement.

## How an assignment flows

1. Muse writes the assignment: the goal in one sentence, the branch name, the exact files and line-level changes, the acceptance criteria, the constraints (the standing rules above), and the validation to run.
2. The implementer checks out the branch, makes the edits, runs local validation, captures desktop (1200px) and mobile (375px) renders in EN and FR with screenshots, pushes the branch, and opens a PR with a completion report (branch and base commit, each fix with file and line, validation results item by item, anything that did not validate stated plainly).
3. Muse reviews the diff and the evidence, runs the verification loop (every claim checked against its primary source), and gives Leis a short verdict: what changed, what was verified, and a clear recommendation.
4. Leis merges on his explicit "Merge." Netlify deploys from main. Muse verifies live after deploy and updates the audit ledger.

## Validation to run before opening a PR

1. Tag-balance check on every changed file.
2. `node --check` on any changed JS.
3. Lychee link check, if available locally.
4. axe-core accessibility scan, if available locally.
5. Render check: desktop (1200px) and mobile (375px), in EN and FR, for every changed page. Capture screenshots.
6. Confirm any changed aria-label or accessible name is correct in both languages.

## Security

- Never put a credential in the repo, in a prompt, or in a shared file.
- No Google Workspace, Ads, Zeffy, Desjardins, or Google Ads API access for implementation work.
- No donor, beneficiary, or banking data in the repo. The repo contains no donor names, emails, amounts, or payment details.
- No home street address in public content or signatures. The registered office is 291 Glynn Avenue, Ottawa ON K1K 1R9. The operating address is never published.
- If access is ever in doubt, Leis revokes the credential and the local clone is the only remaining copy.
