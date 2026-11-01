# MyCodeSpace Genie: Fresh Attempt

Name: `mycodespace-genie`
Start date: 2026-11-01
State: paused; fresh preview ready for owner review
Branch association: `ws-mycodespace-genie/fresh-start`
Target: main; direct-main default; local preview only, no deployment authorized.

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@f38ceada0768

## Goal and Current State

Implemented the [work order](../../work-orders/2026-11-01-mycodespace-genie-overlay.md) from zero at owner request. Previous implementation is preserved on ws-mycodespace-genie/overlay. Fresh branch starts from deployed main 19ced60, carrying only registration/work order from 0914d4b; no old overlay code reused.

Original inline SVG character, outlined bubbles and smoke are in src/components/GenieOverlay.astro. Native CSS keyframes provide rise/grow, eyebrow lift, wink, joke, lamp rub, smoke burst and announcement. Stroke halos and a feathered spotlight improve legibility without opaque panels. During playback main content blurs 5px and fades to 38% opacity with a 250ms transition; a translucent paper-coloured radial field follows the SVG. All exit paths restore main appearance. Existing photo, layout and copy retained.

## Policies and Timing

- Eligibility: ≥951px, primary fine pointer plus hover, no reduced-motion preference. Suppress entirely otherwise, including touch-only tablets. Resizing or preference changes remove playback.
- After 600ms delay: entrance 0–1.6s, eyebrow 1.7–2.35s, wink 2.25–2.8s, joke 2.6–4.9s, rubbing/sparks 4.9–6.15s, smoke 6.15–7.25s, announcement 6.65–9.75s; cleanup at 10s.
- Exact joke “Because myspace.com flopped”; final “!!! We now have MyCodeSpace.AI !!!”. Longer than suggested 7–9s to retain readable pauses.
- Once per tab session, optional sessionStorage; unavailable storage permits repeat playback. Query ?genie=1 forces replay; footer Replay the genie button also replays. Escape or Skip magic dismisses. Focus returns to replay if dismissal held focus; rest of overlay passes clicks through.

## Evidence

- 24 existing browser checks still pass after the legibility change, plus five focused checks: main blur active, bubble transparent, underlying link receives hit-testing, Escape restores appearance, reduced motion restores appearance. Static build and whitespace check pass.
- Legibility refinement: owner asked for a creative separation from underlying text. Added shared moving/feathered spotlight and temporary main-content softening; inspected joke/final screenshots. No opaque fills added to SVG artwork or bubbles. Page remains clickable and normal appearance returns after dismissal/completion/resize.

- Static build and git diff --check pass. No dependencies added.
- 24 Chromium/Playwright checks pass: exact copy; playback; click-through; Escape/pointer/keyboard dismissal; focus return; session suppression; replay; resize; phone/narrow desktop/touch tablet/reduced motion suppression; no overflow; bubble bounds at 951/1920/2560; completion; no browser errors.
- Screenshots of entrance, eyebrow, wink, joke, rub, smoke and final reveal captured outside repo; joke, smoke and announcement visually reviewed at 1440px.
- Main matches origin/main; workflow files unchanged, no synchronization needed. No open owned bugs or intake/mail. Previous claim was from the parked attempt; owner explicitly selected this fresh run.
- No deployment, cloud changes, main integration, or changes to previous implementation branch.

## Next Step

Owner reviews http://localhost:4329/?genie=1 on desktop. Refine artwork/timing from feedback; do not deploy without separate owner authorization.

## Open Threads

- Awaiting human: review of new focus/spotlight treatment. Original transparent overlay was muddled by page text; background softening now separates artwork from content.
- Reduced motion suppresses the cameo instead of showing a still; avoids introducing a persistent overlay needing its own dismissal story.

## External State

Astro dev server left running on port 4329 from this checkout. Restart with npm run dev in mycodespace-site if needed. New branch holds this attempt; old overlay branch remains untouched.

## Document Index

- intake/README.md: incoming item convention.
- intake-dispositions.md: no received items.
