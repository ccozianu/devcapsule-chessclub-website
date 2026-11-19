# Workstream Current Status: Project Management

Name: `project-management`

Start date: `2026-09-27`

State: active; permanent coordination

Definition read: WORKFLOW.md@02914b52c231, WORKFLOW-LOCAL.md@23bcc833e641

Branch association: `ws-project-management/coordination`

## Goal

Maintain project-wide priorities, sequencing, cross-workstream dependencies,
and lifecycle decisions while this repository uses multiple-streams mode.

## Current State

The reserved workstream was initialized. Transitioned from single-stream mode on 2026-09-27.
- Initial site solution (`ag-flash3.8-site`) built with Astro 5 and Tailwind CSS.
- 6-palette theme switcher (Classic Dark, Solarized Light, Nordic Clean, Tournament Green, Midnight Blitz, Gruvbox Warm) implemented and contrast-hardened.
- Content collections structured and aligned with official `smartgalati.ro` instructors (Lucian Gilea, Cristian Dăianu, Robert Pîșu, Flavius Mihailiuc, Robert Ionică, Dănuț Radu).
- Google Cloud Storage deployment suite (`scripts/gcs/`) executed; site is live and verified on HTTPS at `https://smartgalati-test.mycodespace.ai` via Cloud CDN and Google-managed SSL.
- Delivery workstream `2026-09-27-gcs-deployment` completed and integrated; enhanced GCS deployment suite v2 for multi-project deployments, regional Finland storage (`europe-north1`), existing/new load balancers, and Cloud DNS automation; verified live on `https://smartgalati-test2.mycodespace.ai`.

## Planned Next Step

The next coding agent should pick up the [smartgalati-test5 work order](../../work-orders/2026-09-27-smartgalati-test5-prototype.md), register a fresh delivery workstream and implement the independent candidate.

## Latest Delivered Slice (2026-11-19): workflow definition refresh to 0.3.1

- At the owner's explicit request, refreshed the reusable definition from
  0.2.14 to DevCapsule 0.3.1 with `devcapsule bootstrap project
  --refresh-workflow-definition` (tool: v0.3.1-local-linux-x86_64). It
  replaced `AGENTS.md` and `WORKFLOW.md`, set `[workflow] version = "0.3.1"`,
  added `.idea/` to `.gitignore`, and installed `PREAMBLE.md` and
  `INFORMATION-MODEL.md` (for humans). Project-owned files were preserved.
- Migration steps from *Changes* (0.3.0, 0.3.1):
  - *Validation commands are required*: filled that section of
    `WORKFLOW-LOCAL.md` from the sites' `package.json`, READMEs and CI
    workflows. Ran the Rocada gate as written: 10/10 unit tests, contrast
    check passes for all palettes, build 291 pages with no errors. The other
    sites' commands were transcribed, not rerun.
  - *Integration is a merge commit*: updated the wording of the prototype
    direct-main exception in `WORKFLOW-LOCAL.md` from fast-forward to
    `git merge --no-ff`, matching the new direct-main procedure. Agent's
    interpretation: the exception authorizes direct-main delivery, and
    "fast-forward" only restated the old procedure. Owner may reverse it by
    recording a fast-forward exception.
  - *Information model*: no bug record needs reclassifying; 0 open bugs.
  - *Pile of ideas*: no migration; directory is created with the first idea.
- Added the two new files to `index.md`.
- Delivery: pull request from `ws-project-management/workflow-refresh`, at the
  owner's request for this change (direct-main remains the local default).
  The capsule has no `gh` and no token, so the branch is pushed and the owner
  opens and merges the pull request, as a merge commit.

## Earlier Slice (2026-09-27, evening)

- Prepared the test5 work order at the owner's request (hostname confirmed as
  `smartgalati-test5.mycodespace.ai`), carrying forward the test4 conditions plus
  the test4 lessons: content-fidelity audit and reusable verified content, taken
  ports, certificate/host propagation window, CDN header ordering, trailing-slash
  redirects, and the finishing/retire steps of the workflow.
- Linked it from README and index; recorded test4 (`claude-rocada-site`) as
  delivered and integrated. Synchronized this branch from `main` first.
- Delivery: direct-main by rebase + fast-forward + normal push.

## Previous Slice (2026-09-27)

- Prepared the test4 work order at the owner's request, carrying forward the
  test3 conditions, readability/palette refinement, unchanged enrollment URL,
  independent design freedom and shared GCS load balancer constraints.
- Linked it from README and index. No test4 implementation or infrastructure
  has been created; the next agent owns that delivery.
- Synchronization: started the coordination branch from current main because
  the local prototype integration policy changed since this workstream's stamp.
  No open bugs are owned by project-management; mailbox and intake are empty.
- Interpretation: "same conditions" includes the owner's later readability and
  palette requests, but does not prescribe Astra's framework, colors or layout.
- Validation: checked local document links, resource names against existing
  deployment scripts, and diff whitespace. No runtime tests needed for this
  documentation-only slice; live cloud state was not revalidated.
- Delivery: direct-main; target main; integration branch
  ws-project-management/coordination; synchronize/rebase then fast-forward and
  push normally under WORKFLOW-LOCAL.md. No human-only merge step.
- Permanent coordination remains open. No uncommitted work is intended at pause.

## Open Threads

- Owner step: set the GitHub repository's pull-request merge method to merge
  commits (definition 0.3.0 migration); the agent has no repository-settings
  access.
- `.devcapsule/devcapsule.linux-amd64.lock` carries an uncommitted
  re-resolution (matrix embedded-33, Claude Code 2.1.321, Codex 0.167.0) made
  outside this slice; left uncommitted for the owner to decide.
- The planned next step predates `smartgalati-test5-site/`, which now exists
  on `main`; confirm or replace it at the next coordination session.
