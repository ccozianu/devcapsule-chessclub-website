# R-MYCODESPACE-001: MyCodeSpace website

Status: accepted
Priority: gating
Accepted: 2026-11-01, by owner instruction in chat.

- Deliver in `mycodespace-site/`; preserve existing club sites.
- Target domain: https://mycodespace.ai.
- Clearly identify https://devcapsule.mycodespace.ai as the first product,
  with more to follow; make that link the primary action.
- Owner refined the focus on 2026-11-01: a personal google3-like codespace
  for students, hobbyists and professionals. Use the approved headline "Your
  code. Your projects. Your own space." and explain a home for projects, tools,
  and knowledge. Returning to old code is one benefit, not the main pitch.
  DevCapsule is the first step. No broad security or Google affiliation claims.
- Keep copy concise and conversational. Do not promise future products,
  release dates, or permanent compatibility with all historical programs.
- Follow the existing Astro static build and shared GCS deployment approach.
- Provide a readable responsive page, keyboard focus and a custom 404 page.
- Owner authorized live deployment on 2026-11-01 after accepting the page.
  Serve both apex and www over valid HTTPS, using an apex A record and a www
  CNAME. Preserve existing chess websites and DevCapsule DNS.

Validation: static build, browser checks on mobile and desktop, accessibility
scan, primary link verification, and deployment wrapper plan/failure checks.

Contact refinement (owner instruction, 2026-11-01): remove the outbound LinkedIn
post link. Add “Get in touch with Costin”, prominent but subordinate to the
opening paragraph, with email rendered as SVG outlines and links to GitHub and
LinkedIn profiles. This slice must stop before production deployment.

Contact review refinement (2026-11-01): on wide screens, place the contact
invitation beside the explanation in two columns so it does not interrupt the
reading flow. Introduce it with “Curious? Want to find out more? Want to
contribute?” followed by “Get in touch with Costin!” on a separate line.
Use the owner's supplied JPG portrait, moved from the repository root into a
descriptively named site asset. Keep mobile stacked and stop before deployment.

Header refinement (2026-11-01): keep the header band close to its existing
text/wordmark height, remove the redundant “A home for everything you build”
intro announcement, and reduce empty space above the headline on desktop.

Body-flow refinement (2026-11-01): keep contact as a right-hand body column,
beginning beside the lead paragraph, so the paragraph never stretches above
the card. Text may reclaim the full body width below the card; keep the card
out of the header and preserve the stacked mobile reading order.

Alignment refinement (2026-11-01): align the desktop contact card's top edge
with the headline's top, retaining body placement and stacked mobile order.

Portrait refinement (2026-11-01): owner identifies himself as the player on the
left. Crop around him in an oval, preserving sharpness and excluding the partner
on the right from generated public images. This supersedes the full-scene crop.

Portrait positioning refinement (2026-11-01): retain the owner's left-side
position within the card's photo area, using an asymmetric egg-shaped oval
rather than centering the portrait. Keep partner excluded.

Scene framing correction (2026-11-01): use the original full-resolution source
from Git and retain both the player on the left and foreground chessboard in
a wider asymmetric egg. Exclude the partner on the right. Supersedes the
narrow headshot framing; preserve the source unchanged.

Publication approval (2026-11-01): owner accepted the current contact/layout
refinements and explicitly requested production deployment before any genie
overlay. This supersedes the local-only restriction for these changes.

Genie overlay (owner work order, 2026-11-01): add a desktop-only line-art SVG
cameo over the landing page with six beats in order: grow from the
bottom-left, eyebrow gesture and wink, outlined bubble “Because myspace.com
flopped”, lamp rubbing, comic poof, announcement “!!! We now have
MyCodeSpace.AI !!!”. Transparent interiors, clicks pass through, accessible
dismissal, reduced-motion and once-per-visit policies documented. Phones and
touch-only screens never start it. Local preview for owner review first; no
production deployment without separate authorization. See the
[work order](../work-orders/2026-11-01-mycodespace-genie-overlay.md).
