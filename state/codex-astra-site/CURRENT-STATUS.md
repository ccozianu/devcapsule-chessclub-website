# Workstream Current Status: Codex Astra Site

Name: `codex-astra-site`
Start date: `2026-09-27`
State: integrating; owner authorized direct-main delivery
Branch association: `ws-codex-astra-site/implementation`
Target branch: `main`
Designated integration branch: `ws-codex-astra-site/implementation`
Delivery method: direct-main, explicitly authorized by owner on 2026-09-27 and recorded in WORKFLOW-LOCAL.md. No human-only publication or merge step remains.
Synchronization policy: direct-main synchronization and fast-forward procedure. Main matches origin/main; workstream already contains it, so no history rewrite is needed. No force pushes.

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@f38ceada0768

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

Archive the completed workstream, validate the final tree, fast-forward main and push normally; verify remote integration and retire live coordination state.

## Document Index

- `intake/`: read at session start; no pending items.
- `intake-dispositions.md`: consult for coordination decisions; none received.
- [Delivery evidence](../../implementation-notes/website/2026-09-27-codex-astra-site.md): open for validation, deployment resources, known limits, and external state.
- [Site guide](../../../codex-astra-site/README.md): open for development and deployment commands.

## Latest Delivery: Readability and Palettes

- Desktop top-strip text is 14px semibold; shared rem-based tokens improve captions, dates, footer and utility text without changing major page spacing/headlines. All component colors use semantic palette tokens.
- Original Astra default plus Solarized Light, Nord Snow, Catppuccin Latte, Gruvbox Light and Rosé Pine Dawn. Native dropdown in desktop top strip/mobile menu, early preference restoration, persistence, cross-tab synchronization and storage-denied fallback.
- Build: zero errors/warnings/hints; original 19-route browser suite passes. Public HTTPS palette suite passes all six palettes across three representative routes each, five viewport sizes, keyboard/mobile selection and persistence/fallback checks. Zero WCAG A/AA findings in these palette checks.
- Deployed through unchanged shared GCS scripts; invalidated only test3 hostname on shared CDN. Public license/attribution file verified. Original enrollment URL and test2 site preserved.
- Upstream palette sources and license notices documented in the site README and `public/licenses/themes.txt`. Detailed evidence appended to the permanent delivery note.
- No pending intake; all source and documentation changes saved on the workstream branch.

## Integration Authorization

Owner explicitly permitted skipping PRs and directly merging/pushing main during the prototype phase. This supersedes the earlier PR-access blocker. Clean main/origin/main match; no pending mail/intake or workstream-owned open bugs.
