# MyCodeSpace Desktop Genie Overlay

Name: `mycodespace-genie`
Start date: 2026-11-01
State: active
Branch association: `ws-mycodespace-genie/overlay`
Target: main; delivery: direct-main repository default; production deployment
prohibited for this slice (owner wants a local preview first).

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@f38ceada0768

## Goal and Current Task

Implement the [genie overlay work order](../../work-orders/2026-11-01-mycodespace-genie-overlay.md):
a desktop-only line-art SVG cameo over the MyCodeSpace landing page with the
owner's six beats and exact copy, previewed locally on port 4329.

Current task: register the workstream, then implement the overlay in
`mycodespace-site/`.

## Current State and Evidence

- Registered from `main` 19ced60 after the contact workstream closed and
  deployed. The work order itself was carried over from the owner's original
  checkout, where it was still uncommitted.

## Next Step

Implement the overlay, build, run Chromium checks, present the local preview.

## Open Threads

None yet.

## Document Index

- intake/README.md: intake convention; read when receiving mail.
- intake-dispositions.md: received item decisions; empty.
