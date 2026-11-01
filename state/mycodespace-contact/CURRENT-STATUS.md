# MyCodeSpace Contact Update

Name: `mycodespace-contact`
Start date: 2026-11-01
State: paused; prepared for owner review
Branch association: `ws-mycodespace-contact/update`
Target: main; delivery: direct-main repository default, production deployment prohibited for this slice.

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@f38ceada0768

## Goal and Current Task

Remove the LinkedIn post link and add a visible “Get in touch with Costin” section subordinate to the opening paragraph, with an outlined SVG email and GitHub/LinkedIn profiles. Done means a successful static build and responsive browser review, with no deployment.

## Context and Next Step

Owner prioritized MyCodeSpace; the chess-site next step remains recorded in project-management and is deferred during this work.
Starting main equals origin/main; workflow files unchanged. No synchronization needed. No open bugs owned by this new workstream. Mail/intake empty.
Workflow gap: registration instructions describe both creating records on main and committing on the first branch; create and commit registration on the new branch from clean main, as step 6 directs.
Next: owner reviews http://localhost:4329/ and supplies the second change. Do not deploy until explicitly authorized.

## Checkpoint Evidence

- Removed the LinkedIn post link; contact panel follows the lead paragraph. Heading is 20px versus 21px lead on desktop, 17px versus 18px on mobile.
- Email SVG contains glyph paths, no text node or mailto. Spoken-form alt preserves accessibility.
- GitHub verified as github.com/ccozianu. LinkedIn profile slug costin-cozianu-0a36a95 identified from indexed LinkedIn posts; direct profile fetch returns LinkedIn's 999 restriction, so owner can confirm destination during review.
- Static build and git diff --check passed. Chromium at 320, 390, 1440px: no overflow, loaded SVG, correct profile URLs, old post link absent, no page errors. Desktop/mobile screenshots visually reviewed.
- No deployment, cloud upload, DNS or production changes. Local dev server remains on port 4329 for review.
- Source, requirements and site guide updated; committed on this workstream branch. No runtime dependencies added.


## Open Threads

- Awaiting the human: second change has not yet been specified; no production deployment authorized.

## Document Index

- intake/README.md: intake convention; read when receiving mail.
- intake-dispositions.md: received item decisions; empty.
