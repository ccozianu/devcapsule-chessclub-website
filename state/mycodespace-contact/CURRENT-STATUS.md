# MyCodeSpace Contact Update

Name: `mycodespace-contact`
Start date: 2026-11-01
State: paused; ready for owner review
Branch association: `ws-mycodespace-contact/update`
Target: main; delivery: direct-main repository default, production deployment prohibited for this slice.

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@f38ceada0768

## Goal and Current Task

Refine the contact invitation without production deployment. Owner requested a two-column desktop layout, introductory questions, and a supplied JPG portrait moved to a descriptive site asset path.

## Current State and Evidence

- Latest positioning refinement: left-aligned portrait within card instead of centering it; asymmetric CSS egg outline. Underlying sharp crop still excludes partner. Build, diff whitespace and Chromium at 320/390/1440px passed; desktop screenshot reviewed. No deployment.

- Latest owner portrait refinement: owner identified himself as player on left. Astro now generates left-aligned 2:3 crops at 160/320px; CSS oval frames a 160×240px portrait. No blur or generative changes. Partner on right excluded from generated public files; full original stays in source assets only. Built dist contains only cropped WebPs (7/19kB), not original or previous full-scene versions.
- Build, whitespace and Chromium responsive checks passed at 320/390/1440px. Desktop screenshot confirms sharp owner portrait with partner absent. No deployment.

- Latest alignment refinement: moved card before headline in document flow so their tops align on desktop; mobile flex ordering still places card after explanatory text. Build, whitespace checks and Chromium at 320/390/1440px passed. Desktop screenshot reviewed: card and headline begin at y=88px. No deployment.

- Latest owner refinement: prevent the lead from spanning above the contact card. Replaced the lower two-column grid with a right float beginning at the lead. Card remains in body, below headline. Build, whitespace checks and Chromium at 320/390/1440px passed; desktop screenshot reviewed. No production changes.

- Owner requested tighter desktop top spacing: header padding reduced to 8px per side vertically (56px band including wordmark); removed intro announcement and its unused CSS. Headline now starts at y=88px instead of y≈235px at desktop widths. Removed extra-large-screen top padding override.
- Final build and diff whitespace checks passed. Chromium checks at 320/390/1440px still pass; 1600px confirms 56px header, headline at 88px, announcement absent, no horizontal overflow. Desktop screenshot reviewed. No deployment.

- Contact now floats right beginning beside the headline in the body. Lead and explanation wrap beside it and may reclaim width below it. Below 951px, text precedes contact in the stacked layout.
- Copy: “Curious? Want to find out more? Want to contribute?” then “Get in touch with Costin!” on a separate line.
- Static build passed. Chromium at 320, 390 and 1440px: no overflow, email SVG loaded, correct profile URLs, old post link absent, no page errors. Desktop screenshot reviewed.
- Found owner-supplied mycodespace-site/maxresdefault.jpg and moved it to src/assets/costin-cozianu-chess.jpg. Original retained in source assets for editing; latest portrait crop supersedes the initial full-scene display.
- Rebuilt successfully and verified both photo and email load at 320, 390 and 1440px, with no overflow or page errors. Desktop screenshot reviewed. No dependencies added.
- No production deployment or cloud changes. Local dev server remains on port 4329 for review.
- main and origin/main still match; no workflow changes, no synchronization needed. No open owned bugs or mail.
- Chess-site next step remains recorded in project-management and deferred by owner priority.

## Next Step

Owner reviews local preview at http://localhost:4329/. Await further changes; no production deployment without explicit authorization.

## Open Threads

- Awaiting the human: local visual review.
- Original broader second change remains unspecified. Current turn refines the first contact change.

## Document Index

- intake/README.md: intake convention; read when receiving mail.
- intake-dispositions.md: received item decisions; empty.
