# MyCodeSpace Hosting

Name: `mycodespace-hosting`
Start date: 2026-11-01
State: active
Branch association: `ws-mycodespace-hosting/deployment`
Target: main; integration branch: ws-mycodespace-hosting/deployment; delivery: direct-main.

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@f38ceada0768

## Goal and Authorization

Owner accepted the page and explicitly authorized deployment with gcloud,
apex A and www CNAME, HTTPS for both. Preserve all existing neighboring sites.

## Current and Next Task

Deploy a dedicated bucket/backend on the existing original load balancer
(chessclub-site, central-trees-497510-h7), create a two-domain certificate,
add host routing, publish DNS, then verify both public HTTPS endpoints.
Done means both hosts serve the built page with valid TLS and existing sites
remain reachable. Record exact commands/configuration for later updates.

## Session Facts

Current main equals origin/main at e47325f; no synchronization required.
Clean worktree avoids owner's local DevCapsule config edits.
Gcloud is authenticated. Original project has BACKEND_BUCKETS usage 1/3.
Apex and www have no A/AAAA/CNAME records. devcapsule CNAME stays unchanged.
No open bugs belong to this newly registered workstream; intake is empty.

## Documents

- intake-dispositions.md: incoming-work decisions, currently empty.
