# Workstream Current Status: Codex Astra Site

Name: `codex-astra-site`
Start date: `2026-09-27`
State: active
Branch association: `ws-codex-astra-site/implementation`
Target branch: `main`
Delivery: reviewable branch; ordinary integration with deliverable.

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@05687aa6136c

## Goal
Build an independent design in `codex-astra-site/` under the existing work order, and deploy it at `https://smartgalati-test3.mycodespace.ai` through `scripts/gcs`, sharing the test2 load balancer. User authorized implementation and deployment on 2026-09-27. Preserve the enrollment URL `https://forms.gle/smartgalati-inscriere` despite its known non-working state; these are alternative candidates for owner review.

## Current State
- Clean main matches origin/main. Both reserved workstreams exist. No open bugs owned by this new workstream and no intake.
- Read workflow 0.2.14 and local workflow; no definition changes or synchronization needed.
- Live GCP inspection confirms `chessclub-test2-url-map`, `chessclub-test2-https-proxy`, existing certificate `chessclub-test2-cert`, and IP `8.232.113.26` in `mycodespace3p`. Existing default routes to test2 backend.
- Design direction: ivory, forest green, expressive typography, original club photography; Astro static output with Markdown collections.

## Current Task
Implement independent website, content, local smoke checks, deployment configuration, then deploy and verify HTTPS plus existing-site continuity.
Requirements: R-SITE-001 through R-SITE-007.
Done means: complete content routes, accessible responsive UI, archive routing, authoring docs, successful build/browser checks and test3 HTTPS with test2 still operating.

## Planned Next Step
Scaffold site and migrate existing content with an independent layout; configure isolated test3 resource parameters.

## Open Threads
- Existing registration form URL intentionally unchanged and not a blocker.
- Product owner's visual acceptance remains a later comparison of candidates.
- Workflow registration wording conflicts on committing registration to main vs first workstream branch; follow the explicit Beginning A Workstream step 6: register on first workstream branch and integrate with deliverable.

## Document Index
- `intake/`: read at session start; pending coordination items.
- `intake-dispositions.md`: consult for intake decisions; none yet.
