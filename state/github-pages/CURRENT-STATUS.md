# Workstream Current Status: GitHub Pages deployment for Rocada

Name: `github-pages`

Start date: `2026-11-09`

State: active

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@f38ceada0768

Branch association: `ws-github-pages/deployment`

Target branch: `main`. Integration branch: `ws-github-pages/deployment`.
Delivery method: `direct-main` under the prototype-phase exception in
`WORKFLOW-LOCAL.md` (rebase onto `main`, fast-forward, normal push).

## Goal

Give `claude-rocada-site` (test4) a GitHub Pages deployment path beside the
existing Google Cloud Storage scripts and the optional Firebase Spark path:
a GitHub Actions workflow that builds the site and publishes it to the
repository's Pages site, with the site itself made base-path aware so it
works both at `https://<owner>.github.io/<repo>/` and on a custom domain.

Owner request (2026-11-09, chat): "we have a bunch of website versions ...
with a script to deploy to google cloud bucket. Can we also make a version in
which the claude rocada site deploy to github pages?"

## Facts Established At Start

- Repository `ccozianu/devcapsule-chessclub-website` is private (anonymous
  API returns 404; SSH push works). GitHub Pages on a private repository
  needs a paid plan; public repositories get it on GitHub Free. The hosting
  design note warns against making the repository public only for hosting.
- No `gh` CLI and no GitHub token in this environment, so enabling Pages
  (Settings → Pages → Source: GitHub Actions) stays an owner step; the
  `actions/configure-pages` `enablement` input needs a PAT, not `GITHUB_TOKEN`.
- Astro trial build with `--base /devcapsule-chessclub-website`: canonical
  URLs, optimized images and CSS get the prefix automatically; the ~35
  hard-coded `href="/..."` links and the header's active-link check do not.

## Current Task

Register the workstream, then: base-path helper and link updates in the
site, env-driven `site`/`base` in `astro.config.mjs`, Pages workflow,
local build/check script, tests under a base path, deployment guide,
requirement amendment, README/index links.

## Next Resumable Task

Implement the base-path helper and workflow (see Current Task), validate
locally under the Pages base path, then finish by direct-main.

## Open Threads

- Pages enablement and plan eligibility are the owner's; the workflow's
  first run fails at `configure-pages` until Pages is switched on.

## Document Index

- `intake/` — queue; `intake-dispositions.md` — decision log (both empty).
