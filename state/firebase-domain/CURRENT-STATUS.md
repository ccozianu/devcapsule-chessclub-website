# Firebase Custom Domain Scripts

Name: `firebase-domain`
Start date: `2026-09-30`
State: active
Branch association: `ws-firebase-domain/deployment`
Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@f38ceada0768

## Goal

Make the Firebase deployment public URL configurable for custom domains,
including build canonical URLs and HTTP checks. No live deployment or DNS edits.

## Current State

Main/origin agree at a4925bc; no synchronization needed. Existing clean worktree
reused after the prior stream concluded, preserving original checkout's untracked
test5 scripts. No open owned bugs or intake. Test5 remains the portfolio next step.
Follow explicit registration step 6 as in the preceding Firebase workstream.

## Next Step

Implement FIREBASE_SITE_URL validation, check default/custom behavior, and update
the operator guide. Integrate direct-main by rebase/fast-forward/normal push under
WORKFLOW-LOCAL.md. No human-only publication step.

## Document Index

- intake/README.md: incoming work convention.
