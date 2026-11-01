# MyCodeSpace Genie: Fresh Attempt

Name: `mycodespace-genie`
Start date: 2026-11-01
State: paused; local preview accepted, awaiting deployment authorization
Branch association: `ws-mycodespace-genie/fresh-start`
Target: main; direct-main default; local preview only, no deployment authorized.

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@f38ceada0768

## Goal and Current State

Implemented the [work order](../../work-orders/2026-11-01-mycodespace-genie-overlay.md) from zero at owner request. Previous implementation is preserved on ws-mycodespace-genie/overlay. Fresh branch starts from deployed main 19ced60, carrying only registration/work order from 0914d4b; no old overlay code reused.

Original inline SVG character, outlined bubbles and smoke are in src/components/GenieOverlay.astro. Native CSS keyframes provide rise/grow, eyebrow lift, wink, joke, lamp rub, smoke burst and announcement. Existing photo, layout and copy retained.

Owner accepted the final localized readability effect (“This is perfect !!”). Feathered SVG masks restrict 4px backdrop blur and 56% paper tint to the character silhouette and visible speech bubbles. Rest of page remains sharp, with no main opacity/filter changes. Removed opacity animation from flight ancestor so CSS backdrop filters can sample the underlying page; movement/scaling remain animated. This supersedes the previous page-wide focus treatment.
## Policies and Timing

- Eligibility: ≥951px, primary fine pointer plus hover, no reduced-motion preference. Suppress entirely otherwise, including touch-only tablets. Resizing or preference changes remove playback.
- After 600ms delay: entrance 0–1.6s, eyebrow 1.7–2.35s, wink 2.25–2.8s, joke 2.6–4.9s, rubbing/sparks 4.9–6.15s, smoke 6.15–7.25s, announcement 6.65–9.75s; cleanup at 10s.
- Exact joke “Because myspace.com flopped”; final “!!! We now have MyCodeSpace.AI !!!”. Longer than suggested 7–9s to retain readable pauses.
- Once per tab session, optional sessionStorage; unavailable storage permits repeat playback. Query ?genie=1 forces replay; footer Replay the genie button also replays. Escape or Skip magic dismisses. Focus returns to replay if dismissal held focus; rest of overlay passes clicks through.

## Evidence

- Static build and diff whitespace checks pass. No dependencies added.
- 24 Chromium/Playwright checks pass after localization: exact copy; playback; click-through; Escape/pointer/keyboard dismissal; focus return; session suppression; replay; resize; phone/narrow desktop/touch tablet/reduced motion suppression; no overflow; bubble bounds at 951/1920/2560; completion; no browser errors.
- Final joke screenshot visually reviewed: blur follows silhouette/bubble, adjacent text and photo remain sharp. Owner then explicitly accepted visual result.
- Main and production unchanged; no deployment, cloud changes, or edits to previous attempt branch. Mail/intake empty; no owned open bugs.

## Next Step

Local version accepted. Await owner instruction for next work or explicit production deployment authorization. Preview: http://localhost:4329/?genie=1.

## Open Threads

- Awaiting human: whether/when to deploy. Visual acceptance alone does not authorize deployment.
- Reduced motion suppresses the cameo instead of showing a persistent still.

## External State

Astro dev server left running on port 4329 from this checkout. Restart with npm run dev in mycodespace-site if needed. New branch holds this attempt; old overlay branch remains untouched.

## Document Index

- intake/README.md: incoming item convention.
- intake-dispositions.md: no received items.
