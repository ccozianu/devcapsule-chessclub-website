# Workstream Current Status: GCS Deployment

Name: `gcs-deployment`

Start date: `2026-09-27`

State: active; waiting on live test execution

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@05687aa6136c

Branch association: `ws-gcs-deployment/scripts-v2`

## Goal

Enhance scripts/gcs deployment suite to support multi-project deployments (resource project `mycodespace3p`, DNS project `central-trees-497510-h7`), regional Finland GCS buckets, existing and new Load Balancers (cross-project capable), and automated DNS record configuration, incorporating lessons learned from prior runs.

## Current State

- Prepared full deployment suite under `scripts/gcs/` incorporating all requirements and lessons learned:
  1. `config.env`: Centralized environment configuration with default target website `smartgalati-test2`, bucket `test2`, region `europe-north1` (Finland), resource project `mycodespace3p`, DNS project `central-trees-497510-h7` (zone `mycodespace`).
  2. `common.sh`: Common helpers ensuring `gcloud` discovery, non-interactive API enablement (`compute.googleapis.com`, `storage.googleapis.com`, `dns.googleapis.com`), and Org Policy `iam.allowedPolicyMemberDomains` handling.
  3. `01-create-bucket.sh`: Regional storage creation in Finland with uniform bucket-level access and no public-access prevention; handles global namespace collision diagnostics.
  4. `02-configure-website.sh`: Website entrypoints, public viewer binding, automated detection of Org Policy HTTP 412, override generation, and propagation retry loop.
  5. `03-deploy-site.sh`: Astro 5 static build and GCS sync with 1-year immutable edge caching for `_astro/*` assets and 5-minute caching for HTML.
  6. `04-setup-https-loadbalancer.sh`: Automates new External Application Load Balancer setup under `mycodespace3p`.
  7. `04b-add-to-existing-loadbalancer.sh`: Adds websites to existing Load Balancers across projects without allocating additional IPs or interrupting existing sites.
  8. `05-configure-dns.sh`: Automates Cloud DNS `A` record creation in `central-trees-497510-h7` with IP auto-discovery and resolver verification.
  9. `check-status.sh`: Real-time diagnostic probe for DNS, Google-managed SSL status (`PROVISIONING` -> `ACTIVE`), and live HTTPS connectivity.
  10. `README.md`: Comprehensive documentation covering topology, lessons learned, and execution walkthrough.
- All scripts verified for syntax (`bash -n`) and domain default `smartgalati-test2` confirmed across all files.

## Planned Next Step

Await user live execution confirmation for `smartgalati-test2`, then commit and integrate `ws-gcs-deployment/scripts-v2` into `main`.

## Open Threads

- None.
