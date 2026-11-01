# MyCodeSpace Genie: Fresh Attempt

Name: `mycodespace-genie`
Start date: 2026-11-01
State: paused; mobile and replay-lamp preview ready for owner review
Branch association: `ws-mycodespace-genie/fresh-start`
Target: main; direct-main default; local preview only, no deployment authorized.
Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@f38ceada0768

## Goal and Current State

Implemented the [amended work order](../../work-orders/2026-11-01-mycodespace-genie-overlay.md): original SVG genie cameo now supports mobile, with a folding replay lamp. Earlier desktop-only attempt remains on ws-mycodespace-genie/overlay. Fresh implementation starts from deployed main 19ced60 plus registration/work order only.

Owner accepted localized focus treatment before this amendment: 4px blur/56% paper tint masked to character and visible bubbles; the rest of the page stays sharp. This is retained. Existing page, contact card and photo framing remain intact.

## Responsive Composition and Behavior

- Desktop: bottom-left entrance and accepted scene. Phones/touch tablets now eligible; portrait uses 480×760 scene with bubbles above character, landscape uses enlarged bubbles in compact wide scene. Mobile rises from below.
- Scene width constrained by both viewport dimensions; dynamic viewport overlay and safe-area-aware controls. Smoke expansion limited to fit, including short screens. Resizing/orientation changes safely dismiss and recompute layout.
- After 600ms: same grow/brow/wink/joke/rub/smoke/reveal beats, exact copy. At 9.75s genie folds into the fixed bottom-right lamp over 700ms, then lamp gives a small landing pulse. Lamp remains for unlimited pointer/touch/keyboard replay.
- Once per tab session using optional sessionStorage; same session key as prior preview. ?genie=1 forces replay. Missing storage allows repeat on reload. Reloads retain lamp even when autoplay is suppressed.
- Skip magic/Escape immediately dismiss; keyboard focus returns to lamp when appropriate. Page clicks and scrolling pass through outside controls. No modal/focus trap.
- Reduced motion: no autoplay, entrance, folding or pulse. Explicit lamp activation shows stationary character and joke until dismissed.

## Evidence

- Static build and diff whitespace checks pass. No dependencies added.
- 75 Chromium checks across 320×568, 390×844, 430×932, 768×1024, 844×390, 1440×1000, 1920×1080: art/bubble/smoke bounds, overflow, errors, dismissal, touch/pointer replay; natural fold completion and persistent lamp; session reload; rotation; reduced-motion static joke; keyboard replay/focus return.
- 35 additional bounds checks at 320×480, 360×640, 480×320, 600×320, 844×390, 950×600, 951×600, including late smoke frames. These exposed smoke spilling on short screens; capped mobile/desktop expansion and verified bounds.
- Portrait phone joke/final and landscape joke screenshots reviewed. Headless Chromium emulation only; owner visual review on actual phones remains useful.
- Main/production unchanged, no cloud changes, no changes to prior attempt branch. Mail/intake empty, no open owned bugs. Workflow files unchanged; no synchronization needed.

## Next Step

Owner reviews http://localhost:4329/?genie=1 on phone and desktop, including the folding lamp. Refine from feedback; do not deploy without separate explicit authorization.

## Open Threads

- Awaiting human: mobile layout and lamp-fold acceptance. Earlier visual acceptance covered the desktop focus treatment only.
- Lamp placement is bottom-right with safe-area insets; can move if it obscures preferred page content.

## External State

Astro dev server left running on port 4329 from this checkout. Restart with npm run dev in mycodespace-site if needed.

## Document Index

- intake/README.md: incoming item convention.
- intake-dispositions.md: no received items.
