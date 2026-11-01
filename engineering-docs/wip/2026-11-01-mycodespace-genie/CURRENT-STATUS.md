# MyCodeSpace Desktop Genie Overlay

Name: `mycodespace-genie`
Start date: 2026-11-01
State: paused; ready for owner review of the local preview
Branch association: `ws-mycodespace-genie/overlay`
Target: main; delivery: direct-main repository default; production deployment
prohibited for this slice (owner wants a local preview first).

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@f38ceada0768

## Goal and Current Task

Implement the [genie overlay work order](../../work-orders/2026-11-01-mycodespace-genie-overlay.md):
a desktop-only line-art SVG cameo over the MyCodeSpace landing page with the
owner's six beats and exact copy, previewed locally on port 4329.

Last task: first implementation, built and verified locally. Status: done,
awaiting owner review.

## Current State and Evidence

- Registered from `main` 19ced60 after the contact workstream closed and
  deployed. The work order was carried over from the owner's original
  checkout, where it was still uncommitted.
- Implementation: `mycodespace-site/src/components/GenieOverlay.astro`
  (inline SVG, CSS keyframes, ~50 lines of sequencing script), included from
  `src/pages/index.astro`. Rules are documented in the site README under
  “Genie overlay” and summarized in the requirements record.
- Timeline from playback start: grow 0–1.4s, eyebrow 1.4–2.2s, wink
  2.1–2.7s, joke bubble 2.6–4.8s, lamp rub with sparkles 4.8–6.2s, poof 6.2s,
  announcement 6.6–9.4s, fade to removal by 10.2s. About one second longer
  than the suggested 7–9s so the announcement holds long enough to read.
- Chosen policies: eligible at ≥951px with `(hover: hover) and (pointer: fine)`;
  reduced motion suppresses it entirely; once per tab session via
  `sessionStorage`; `/?genie=1` replays; Escape, the button (pointer or
  Tab + Enter) dismiss; shrinking below 951px mid-play removes it.
- `npm run build` passes; `git diff --check` clean. Headless Chromium 1243
  (Playwright 1.63 from `claude-rocada-site/node_modules`): 27 checks pass
  with no console or page errors: plays at 951/1440/1920/2560px; removed
  after fade; no replay on reload; replay switch; clicks reach the header
  link and the page scrolls under the overlay; Escape, click and keyboard
  dismissal; no horizontal overflow; shrink removes; reduced motion, 320/390
  phone, 1024 touch tablet and 950px desktop all suppress it with the contact
  photo and layout intact.
- Screenshots of every beat and zoomed face/announcement crops reviewed
  visually at 1440×900 and 2560×1440; kept outside the repository in the
  session scratchpad.
- No deployment, no cloud or DNS changes, no dependency changes.

## Next Step

Owner reviews http://localhost:4329/ (append `?genie=1` to replay). On
acceptance: integrate to `main` by direct-main; production deployment remains
a separate owner authorization.

## Open Threads

- Awaiting the human: visual review of character design, bubble placement
  and timing. The joke bubble sits to the upper left of the head and overlaps
  the headline's second line at 1440px; text stays legible through a
  paper-coloured halo. Alternatives (bubble above or right of the head) overlap
  the lead text or the contact card instead.
- Weighed and unresolved: reduced motion suppresses the cameo rather than
  showing a still frame; a still frame would need its own dismissal story.
- Deliberately not preserved: the rejected alternative copy; the work order
  records it.

## External State

`npm run preview` is serving the current `dist/` on port 4329 in the
background from `mycodespace-site/`; stop it before `npm run dev`.

## Document Index

- intake/README.md: intake convention; read when receiving mail.
- intake-dispositions.md: received item decisions; empty.
