# Firebase Spark Deployment Workstream

Name: `firebase-spark`
Start date: `2026-09-30`
State: active
Branch association: `ws-firebase-spark/deployment`
Target: main; delivery direct-main under WORKFLOW-LOCAL.md (rebase, fast-forward, normal push).

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@f38ceada0768

## Goal / Current Task

Generate scripts for claude-rocada-site static deployment to a separate unbilled Firebase Spark project. Owner requested scripts, not a live deployment or DNS cutover.
Done means project setup, fail-closed billing guard, static-only deployment, status checks, documentation, and tested refusal of billed/unknown targets plus local build/Hosting behavior.

## Current State

- Main and origin/main agree at 0d3e1ab. New clean worktree /tmp/chessclub-firebase-spark preserves unrelated untracked test5 files in original checkout. No upstream synchronization necessary.
- Workflow 0.2.14 and local direct-main policy read. Following explicit registration step 6 (first-branch commit then publish), resolving its contradictory branch-before-registration wording as in hosting-research.
- Both reserved streams present; no open bugs owned by firebase-spark, intake/mail empty.
- Recorded portfolio next step remains test5 work order, reprioritized by this request.
- Scope: extend R-SITE-007 for optional Spark Hosting deployment. No billing links, paid products, DNS changes, or removal of existing GCS resources.
- gcloud exists at /home/devcapsule/xtras/google-cloud-sdk/bin/gcloud, outside initial PATH. Prior research's no-binary limitation was incomplete; this task will locate it like the GCS suite.

## Next Step

Implement scripts and user guide; verify CLI command behavior, billing guard, local build and Firebase emulator serving.

## Document Index

- intake/README.md: received-work convention; read at session start.
- intake-dispositions.md: receipt decisions, currently empty.

## Open Threads

Project ID and operator login are supplied at execution time. No live Firebase deployment is part of script generation.
