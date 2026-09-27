# Workstream Current Status: GCS Deployment

Name: `gcs-deployment`

Start date: `2026-09-27`

State: active; step 2 verified, testing in progress

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@05687aa6136c

Branch association: `ws-gcs-deployment/scripts-v2`

## Goal

Enhance scripts/gcs deployment suite to support multi-project deployments (resource project `mycodespace3p`, DNS project `central-trees-497510-h7`), regional Finland GCS buckets, existing and new Load Balancers (cross-project capable), and automated DNS record configuration, incorporating lessons learned from prior runs.

## Current State

- Resolved Org Policy automation in `scripts/gcs/common.sh` and `scripts/gcs/allow-all-domains.yaml`:
  1. Added automated check & enablement for `orgpolicy.googleapis.com` API on `PROJECT_ID`.
  2. Set `scripts/gcs/allow-all-domains.yaml` to concrete `mycodespace3p` project reference.
  3. Added dynamic in-place substitution in `common.sh` (`override_domain_restricted_sharing`) so `allow-all-domains.yaml` is automatically updated for the active project without any manual YAML editing or placeholders.
  4. Tested and verified `02-configure-website.sh`: Org Policy override applied to `mycodespace3p`, 15-second propagation buffer waited, and `allUsers` successfully granted `roles/storage.objectViewer` on `gs://test2-smartgalati-mycodespace`.

## Planned Next Step

Await confirmation of steps 3–6 from the user, then commit and push changes on `ws-gcs-deployment/scripts-v2` and integrate into `main`.

## Open Threads

- None.
