# Workstream Current Status: Codex Astra Site

Name: `codex-astra-site`
Start date: `2026-09-27`
State: active
Branch association: `ws-codex-astra-site/implementation`
Target branch: `main`
Delivery: pull-request to `main`; branch published. GitHub connector returned HTTP 404 when creating the draft PR, so integration remains pending repository API access or a human-created PR. No direct-main permission inferred.
Designated integration branch: `ws-codex-astra-site/implementation`.
Synchronization policy: merge main into published branch when needed; main and origin/main currently match; no force pushes.

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
Finish browser/accessibility validation, deploy final revisions, verify managed HTTPS and existing-site continuity.

## Open Threads
- Existing registration form URL intentionally unchanged and not a blocker.
- Product owner's visual acceptance remains a later comparison of candidates.
- GitHub connector cannot create a PR for this repository (HTTP 404); SSH branch push succeeded.
- External Lichess iframe has upstream contrast findings once loaded; own-page accessibility checks pass. See delivery evidence.
- Workflow registration wording conflicts on committing registration to main vs first workstream branch; follow the explicit Beginning A Workstream step 6: register on first workstream branch and integrate with deliverable.

## Document Index
- `intake/`: read at session start; pending coordination items.
- `intake-dispositions.md`: consult for intake decisions; none yet.

## Implementation Checkpoint
- Independent Astro 5 site implemented: 20 routes, 6 coach profiles, 7 news articles, 3 performance records, 3 albums/51 photos, course/about/team/contact/support pages, chess demo, and 404.
- Build passes with 0 errors/warnings/hints; three archive boundary tests pass; dev server returns HTTP 200 on port 4323. Browser checks in progress against production preview on port 4324.
- Dedicated bucket and backend created using unchanged shared GCS scripts; hostname routed on shared `chessclub-test2`; new certificate attached while original certificate/default backend preserved. DNS A resolves to `8.232.113.26`; certificate currently provisioning.
- Enrollment link unchanged by explicit user direction. Removed unrelated fake album/study links from this candidate only. Preserved historical source dates.
- CMS remains optional per work-order overview: IDE/GitHub Markdown editing delivered. No new cloud credentials or CI identity created; workflow supports existing Workload Identity variables if configured.
- Mainline remains unchanged; source work is on this workstream branch.

## Validation Checkpoint
- Production browser suite passes 19 content routes and internal targets, menu/filter/contact/gallery keyboard behaviors, and responsive widths 320–1440px. Zero site-owned WCAG A/AA findings on eight representative pages.
- Working Lichess board verified separately, including blocked-service fallback.
- Latest deployment uses the original GCS scripts without shared changes. DNS and host routing verified; test2 continues HTTPS 200. Waiting for new certificate activation before public-domain smoke checks.
- Source branch pushed to origin. Latest source refinements and evidence pending final checkpoint commit.
- Permanent evidence: `engineering-docs/implementation-notes/website/2026-09-27-codex-astra-site.md` (open for validation/deployment details).
