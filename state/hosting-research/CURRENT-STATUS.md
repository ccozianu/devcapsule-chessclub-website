# Workstream Current Status: Hosting Research

Name: `hosting-research`
Start date: `2026-09-30`
State: active
Branch association: `ws-hosting-research/analysis`
Target branch: `main`
Delivery: `direct-main` under WORKFLOW-LOCAL.md; synchronize, rebase and fast-forward; no production cutover.

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@f38ceada0768

## Goal and Current Task

Research the real cost of the scripts/gcs deployment and compare static hosting alternatives; deliver a sourced engineering design note. Done means an explicit standalone/shared cost model, usage assumptions, provider tradeoffs, recommendation and invoice-validation limits, with arithmetic and document links checked.

## Current State

- Started from main at 4265f2b, identical to origin/main; no synchronization changes needed. Both workflow files read at declared release 0.2.14.
- Main checkout has unrelated untracked test5 deployment scripts. Work uses /tmp/chessclub-hosting-research to preserve them; /workspace sibling worktree creation was denied by the filesystem.
- Mailbox empty; no open bugs owned by hosting-research. Both reserved workstreams exist.
- Recorded portfolio next step remains the test5 work order; this owner-requested research takes priority for this slice.
- Workflow judgment: the new-stream procedure asks for registration on the first branch but also disallows a branch predating registration; use its explicit step 6 (register and commit on first branch from main), then publish before research edits.
- No gcloud binary is available here. Repository topology can be established; live resources, usage and billing cannot be authenticated from this environment.

## Next Task

Integrate the completed note by direct-main, then retire this research workstream. Any migration or billing reconciliation is a separately selected follow-up.

## Document Index

- intake/README.md: intake convention; read at session start.
- intake-dispositions.md: decisions on received items; empty at initialization.

## Open Threads

No hosting choice adopted and no cloud resources changed. Actual invoice reconciliation requires billing data.

## Research Checkpoint

- Delivered a sourced comparison of GCS, GitHub Pages, Cloudflare, Firebase, AWS, Azure, Netlify and Vercel, with R2/server alternatives, portfolio allocation and migration acceptance checks.
- Calculations: illustrative 10-GiB/100k-request GCS month is $19.395 standalone, $7.095 allocated among three equal sites, $0.945 incremental. No invoice claimed.
- Validated: source rates/limits, AWS S3 Ireland and Azure West Europe public price feeds, measured existing dist artifacts, formula arithmetic and local note links. No application tests required for documentation only.
- Not validated: authenticated resources, usage, invoices, Finland-specific storage quote, or live provider performance. Pricing guide discrepancies explicitly recorded.
- External state: only workflow coordination published; no hosting resources or DNS changed.
- Uncommitted deliverable: engineering note, index and this status. Original checkout's test5 files untouched.
