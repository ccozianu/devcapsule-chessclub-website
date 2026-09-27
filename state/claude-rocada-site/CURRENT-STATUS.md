# Workstream Current Status: Claude Rocada Site

Name: `claude-rocada-site`

Start date: `2026-09-27`

State: active; implementation in progress

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@f38ceada0768

Branch association: `ws-claude-rocada-site/implementation`

Target branch: `main`

Delivery method: `direct-main` (owner-authorized prototype exception in `WORKFLOW-LOCAL.md`); synchronize by rebase onto `main`, fast-forward and push normally; never force-push `main`. No human-only merge step.

## Goal

Deliver the independent **smartgalati-test4** candidate commissioned by the
[test4 work order](../../work-orders/2026-09-27-smartgalati-test4-prototype.md):
its own design ("Rocada"), Markdown content, six palettes, gallery, archive,
Lichess demonstration, local development, and a live GCS preview at
`https://smartgalati-test4.mycodespace.ai` through the shared `chessclub-test2`
load balancer, then integrate under the prototype policy.

Candidate source directory: `claude-rocada-site/` (`SITE_DIR=claude-rocada-site`),
chosen as a descriptive name in the same spirit as the earlier candidates.

## Current Task

Scaffold `claude-rocada-site/` (Astro 5 static, custom CSS tokens, content
collections), convert factual content from the original `smartgalati.ro` pages
and its 134 public news posts, build pages, components, palettes and tests.

## Next Resumable Task

Validate locally (build, tests, browser/accessibility checks), provision the
test4 bucket/backend/certificate/DNS with the shared scripts, verify live HTTPS
plus test2/test3 continuity, write evidence, then finish and integrate.

## Open Threads

- Factual audit: several records in earlier candidates (2022 Cupa României
  bronze, 2023 junior festival medal counts, 2024 Divizia B silver, weekly
  schedule, several 2022–2024 news stories) could not be found on the original
  site. This candidate uses only content confirmed on `smartgalati.ro`; see the
  content README for items still needing owner confirmation.

## Document Index

- `intake/README.md` — intake queue (open only when an item arrives).
- `intake-dispositions.md` — decisions on removed intake items.
