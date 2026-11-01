# MyCodeSpace Copy Update

Name: `mycodespace-copy`
Start date: 2026-11-01
State: active
Branch association: `ws-mycodespace-copy/update`
Target: main; delivery: direct-main; integration branch: ws-mycodespace-copy/update.

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@f38ceada0768

## Goal and Current Task

Owner approved the proposed broader personal-codespace copy and requested a
live update. Replace the preservation-focused headline with Your code. Your
projects. Your own space. Explain the personal google3 analogy for students,
hobbyists and professionals, and keep DevCapsule as the first step.
Done means static build, mobile/desktop layout checks and correct copy live at
both HTTPS hosts. No security guarantees or speculative product claims.

## Session and Next Step

Current main equals origin/main at 1e7698a; no synchronization needed. Original
checkout's local DevCapsule changes are isolated by this clean worktree.
No open bugs belong to this workstream. Intake empty.
Next: edit copy and metadata, deploy update, verify both hosts, integrate.

## Documents

- intake-dispositions.md: received-item decisions.

## Verification

Static build and GCS update passed. CDN invalidations completed only for apex
and www. Both HTTPS responses match built HTML byte-for-byte, including new
headline, google3 paragraph and metadata; old headline absent. Chromium on both
hosts at 390/1440 px passed layout, accessibility (zero axe violations), primary
link and page-error checks. Source background verified against Google's paper:
https://research.google/pubs/why-google-stores-billions-of-lines-of-code-in-a-single-repository/.
No hosting infrastructure or DNS changes. Next: finish and integrate.
