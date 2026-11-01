# Work Order: MyCodeSpace Desktop Genie Joke Overlay

Date: 2026-11-01
Status: captured for later pickup; implementation progress must be checked in the main conversation/checkout
Requested by: Costin Cozianu
Scope: `mycodespace-site/`; local preview first; no production deployment authorized

## Outcome

Create a playful SVG animation over the MyCodeSpace landing page, on desktop
browsers only. A transparent overlay contains an Aladdin-style lamp character
rendered in thin wireframe/outline strokes, with outlined speech bubbles and
smoke. The page remains visible behind the performance.

This work order preserves the discussion so work can resume after an
interruption. Saving it does not start, cancel, pause, or assert completion of
any implementation already underway in the main conversation.

## Owner-requested sequence

1. The character starts small at the bottom-left of the viewport.
2. He grows larger as he moves toward the center.
3. He performs an expressive eyebrow gesture and wink.
4. An outlined speech bubble says: **“Because myspace.com flopped”**.
5. He rubs his lamp.
6. A comic “poof” smoke explosion reveals the final announcement:
   **“!!! We now have MyCodeSpace.AI !!!”**

Keep the character, bubbles, and smoke as line art, with transparent interiors
rather than opaque panels. Preserve the humorous timing and clear readability.
Use an original Aladdin-inspired character design appropriate for the site's
simple visual style.

## Copy decision

The owner explicitly preferred **“Because myspace.com flopped”** as short and
to the point. Keep it. The alternative “MySpace was taken. So we added code.”
was suggested by the assistant and was not selected.

The final announcement above normalizes the owner's typing to the existing
brand spelling, MyCodeSpace.AI. Exact punctuation and lettering can be refined
during local visual review; do not silently replace the first joke.

## Suggested implementation defaults, subject to review

These were assistant recommendations, not separately accepted owner requirements:

- A short cameo of about 7–9 seconds, then fade away completely.
- Play once per visit; define the visit/session behavior when implementing.
- Include a small accessible dismiss control.
- Allow clicks through the overlay apart from its controls.
- Respect reduced-motion preferences; prefer a still, unobtrusive version or
  suppress the animation, and record the chosen behavior.
- Use native SVG with CSS and only the JavaScript needed for sequencing,
  dismissal, and replay policy. Keep the static site lightweight.

Desktop-only eligibility needs a concrete breakpoint and input policy. Choose
and document a sensible default consistent with the existing responsive site;
verify that phones and touch-only small screens never start the overlay.

## Acceptance and evidence

- Local preview demonstrates every beat in order, including the eyebrow/wink,
  exact first joke, lamp rubbing, and smoke reveal.
- Character, bubbles, and smoke remain legible at representative desktop sizes.
- Animation ends cleanly; no invisible layer blocks page links or scrolling.
- Dismissal works by keyboard and pointer; reduced-motion and repeat-visit
  behavior match the documented choices.
- Mobile layout, contact card, owner photo framing, and existing page copy
  remain intact. Check desktop resizing and narrow-screen suppression.
- Run `npm run build` in `mycodespace-site/`, inspect browser errors, and record
  responsive visual checks and any unfinished animation details.
- Present the local preview for owner review before any live deployment.

## Pickup instructions

Read the repository workflow and current live state before editing. Inspect the
current branch and any existing overlay implementation first; do not duplicate
or overwrite work done after this discussion. Follow the repository workstream
routing for the actual implementation.

The contact refinements currently have their own
[status file](../wip/2026-11-01-mycodespace-contact/CURRENT-STATUS.md).
Use the [site guide](../../mycodespace-site/README.md) for local commands
(port 4329) and hosting context. Production deployment remains a separate owner
authorization. This side-conversation capture changes documentation only.
