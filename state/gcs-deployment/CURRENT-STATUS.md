# Workstream Current Status: GCS Deployment

Name: `gcs-deployment`

Start date: `2026-09-27`

State: active; preparing deployment scripts v2

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@05687aa6136c

Branch association: `ws-gcs-deployment/scripts-v2`

## Goal

Enhance scripts/gcs deployment suite to support multi-project deployments (resource project `mycodespace3p`, DNS project `central-trees-497510-h7`), regional Finland GCS buckets, existing and new Load Balancers (cross-project capable), and automated DNS record configuration, incorporating lessons learned from prior runs.

## Current State

- Workstream registered from `main`.
- Analysis completed:
  1. Multi-project decoupling: resources in `mycodespace3p`, DNS in `central-trees-497510-h7`.
  2. Storage bucket: regional to Finland (`europe-north1`), standard class, parameterized bucket name (`test2`).
  3. Load Balancer flexibility: support creating a new load balancer in `mycodespace3p` OR adding new websites/domains to an existing load balancer (e.g. in `central-trees-497510-h7` or `mycodespace3p`) via URL map path-matching and target proxy SSL certificate updates.
  4. DNS automation: automated Cloud DNS A-record creation in `central-trees-497510-h7` zone `mycodespace`.
  5. Lessons learned: Org policy `iam.allowedPolicyMemberDomains` handling, API enablement checks, and SSL provisioning status monitoring.

## Planned Next Step

Implement the parameterized and modular scripts in `scripts/gcs/` and update `scripts/gcs/README.md`.

## Open Threads

- None.
