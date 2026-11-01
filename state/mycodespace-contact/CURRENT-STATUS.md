# MyCodeSpace Contact Update

Name: `mycodespace-contact`
Start date: 2026-11-01
State: blocked; portrait file not visible
Branch association: `ws-mycodespace-contact/update`
Target: main; delivery: direct-main repository default, production deployment prohibited for this slice.

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@f38ceada0768

## Goal and Current Task

Refine the contact invitation without production deployment. Owner requested a two-column desktop layout, introductory questions, and a supplied JPG portrait moved to a descriptive site asset path.

## Current State and Evidence

- Contact now sits beside the longer explanation on desktops; headline and lead remain full width. Below 951px, explanation precedes contact.
- Copy: “Curious? Want to find out more? Want to contribute?” then “Get in touch with Costin!” on a separate line.
- Static build passed. Chromium at 320, 390 and 1440px: no overflow, email SVG loaded, correct profile URLs, old post link absent, no page errors. Desktop screenshot reviewed.
- Photo is not visible in repository root or nearby workspace paths yet. Asked owner for filename/path or confirmation once copied. Do not substitute a different photo. Once available, inspect it, move to mycodespace-site/src/assets/costin-cozianu.jpg and use Astro image optimization for the contact portrait.
- No production deployment or cloud changes. Local dev server remains on port 4329 for review.
- main and origin/main still match; no workflow changes, no synchronization needed. No open owned bugs or mail.
- Chess-site next step remains recorded in project-management and deferred by owner priority.

## Next Step

Await the missing JPG, then add and verify portrait at desktop/mobile sizes. No production deployment without explicit authorization.

## Open Threads

- Awaiting the human: supplied JPG is absent from this checkout; filename/path requested.
- Original broader second change remains unspecified. Current turn refines the first contact change.

## Document Index

- intake/README.md: intake convention; read when receiving mail.
- intake-dispositions.md: received item decisions; empty.
