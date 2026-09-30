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

Inspect deployment evidence, verify provider pricing against primary sources and write engineering-docs/design-notes/hosting/2026-09-30-static-hosting-costs-and-alternatives.md.

## Document Index

- intake/README.md: intake convention; read at session start.
- intake-dispositions.md: decisions on received items; empty at initialization.

## Open Threads

No hosting choice adopted and no cloud resources changed. Actual invoice reconciliation requires billing data.
