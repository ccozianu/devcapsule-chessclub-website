# Workstream Current Status: Codex Astra Site

Name: `codex-astra-site`
Start date: `2026-09-27`
State: paused; preview delivered, awaiting design review and integration
Branch association: `ws-codex-astra-site/implementation`
Target branch: `main`
Designated integration branch: `ws-codex-astra-site/implementation`
Delivery method: pull-request (repository default); source branch pushed to origin.
Synchronization policy: merge main into published branch when needed; no force pushes. Main matched origin/main at final fetch.

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@05687aa6136c

## Goal

Independent website in `codex-astra-site/` under R-SITE-001 through R-SITE-007, deployed with existing `scripts/gcs` at `smartgalati-test3.mycodespace.ai`, sharing the test2 load balancer. Implementation and deployment authorized by user on 2026-09-27. Enrollment URL explicitly retained despite known non-working state. This is an alternative candidate for owner comparison, not production cutover.

## Current State

- Delivered at **https://smartgalati-test3.mycodespace.ai**; managed certificate ACTIVE and HTTPS verified.
- 20 static pages, independent Astro source/content/assets, Markdown templates and authoring docs, 51 optimized gallery photos, archive routing and working chess embed.
- Dedicated bucket `test3-smartgalati-mycodespace` in `mycodespace3p/europe-north1`; existing `chessclub-test2` LB/IP `8.232.113.26`. Test2 default backend/certificate preserved and verified HTTPS 200.
- Shared GCS scripts unchanged; isolated candidate wrapper supplies deployment parameters.
- Source committed and pushed. GitHub connector returned HTTP 404 on draft-PR creation; SSH branch push succeeded. Integration remains pending PR creation/review; no direct-main permission inferred.
- No pending intake or workstream-owned open bugs.

## Validation

- Build: 20 pages, 0 errors/warnings/hints. Three archive boundary tests pass.
- Public-domain browser suite: 19 content routes, 19 internal targets; menu/filter/contact/gallery keyboard interactions; 320–1440px home viewports; eight representative mobile pages. No site-owned WCAG A/AA findings.
- Hosted custom 404 and trailing-slash 301 verified. Lichess board renders; page remains usable when Lichess is blocked.
- Local mobile Lighthouse: 99 performance, 100 accessibility, 100 best practices, 100 SEO. Lab LCP 2.0s; not a universal sub-second guarantee.
- Dev server remains on port 4323. Screenshots in `/tmp/astra-live-browser/` are ephemeral; durable evidence linked below.

## Open Threads

- Owner chooses among design candidates; source content facts should be confirmed before production.
- Enrollment URL intentionally unchanged; external availability not an experiment gate.
- Third-party Lichess player/move labels have upstream contrast issues after frame load; reported separately from site-owned checks. Both themes tested; direct-link alternative provided.
- CI build/test workflow provided. Optional CI deployment requires configured Workload Identity repository variables; local authenticated deployment is operational.
- PR creation requires repository API access or human use of the published branch compare page. No merge performed.
- Registration wording conflict resolved using explicit Beginning A Workstream step 6: registration committed to first workstream branch and will integrate with deliverable.

## Planned Next Step

Review the live design with the owner; create/review the pull request from `ws-codex-astra-site/implementation` to `main` when repository API access is available. Integrate only through the normal authorized review path; retain this open workstream until then.

## Document Index

- `intake/`: read at session start; no pending items.
- `intake-dispositions.md`: consult for coordination decisions; none received.
- [Delivery evidence](../../implementation-notes/website/2026-09-27-codex-astra-site.md): open for validation, deployment resources, known limits, and external state.
- [Site guide](../../../codex-astra-site/README.md): open for development and deployment commands.
