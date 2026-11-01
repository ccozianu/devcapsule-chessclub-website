# MyCodeSpace

Small English landing page for https://mycodespace.ai. DevCapsule is the first
product; the broader aim is a personal home for code, projects, tools, and
project knowledge, for students, hobbyists and professionals.

Copy draws on the owner’s original post and the
[DevCapsule website](https://devcapsule.mycodespace.ai/). It describes the broader
aim as an ambition. The owner approved the personal google3 analogy on
2026-11-01. Google’s shared-codebase background is documented in
[Google’s repository paper](https://research.google/pubs/why-google-stores-billions-of-lines-of-code-in-a-single-repository/).
This is not a claim of Google affiliation or a security guarantee.

## Local development

From this directory:

```bash
npm ci
npm run dev
```

Open http://localhost:4329. `npm run build` produces static files in `dist/`;
`npm run preview` serves the build on the same port. Stop dev before preview.
There is no backend, analytics, remote font, or account setup. The only browser
JavaScript is the few lines that sequence the genie overlay described below.

Edit `src/pages/index.astro` for copy and `src/styles/global.css` for appearance.
The short page deliberately keeps content in one file rather than adding a CMS.
`src/pages/404.astro` is the custom error page. Public assets include the favicon,
robots.txt and single-page sitemap.

## Genie overlay

`src/components/GenieOverlay.astro` is a desktop-only line-art cameo: a genie
grows from the bottom-left corner, raises an eyebrow and winks, says “Because
myspace.com flopped”, rubs his lamp, and vanishes in a “poof” cloud that
reveals “!!! We now have MyCodeSpace.AI !!!”. Everything is inline SVG with
transparent interiors, driven by CSS keyframes; the script only decides
eligibility, dismissal and removal. The page stays usable underneath: the
overlay ignores pointer events except on its “Skip the genie” button.

Rules, chosen on 2026-11-01:

- Eligible only when the viewport is at least 951px wide (the existing desktop
  layout breakpoint) and the primary input is a fine, hovering pointer, so
  phones and touch-only tablets never start it. Shrinking the window below the
  breakpoint mid-play removes it.
- Suppressed entirely under `prefers-reduced-motion: reduce`; there is no
  still version.
- Plays once per browser tab session (`sessionStorage`); a visit with
  `/?genie=1` replays it for review.
- Dismiss with the button (pointer or Tab + Enter) or the Escape key. The
  cameo lasts about ten seconds, then fades and removes itself.
- Without JavaScript the overlay stays hidden.

Adjust timing in the component's keyframe delays; the beat table is in a
comment above them. Keep the two lines of copy exactly as written above.

## GCS deployment

Live addresses: https://mycodespace.ai/ and https://www.mycodespace.ai/.
Both serve this site; the canonical URL is the apex.

The wrapper uses the repository's [shared upload script](../scripts/gcs/README.md)
and a scoped provisioning helper. Defaults in `scripts/deployment.env` identify
only this site's resources:

| Resource | Value |
|---|---|
| GCP project (storage, load balancer, DNS) | `central-trees-497510-h7` |
| Dedicated bucket | `mycodespace-ai-site-central-trees-497510-h7` |
| Shared load balancer | `chessclub-site` |
| Shared IP | `34.120.230.82` |
| Backend bucket | `mycodespace-ai-site-backend` |
| Host matcher | `mycodespace-ai-site-matcher` |
| Managed certificate | `mycodespace-ai-apex-www-cert` |
| DNS zone | `mycodespace` |
| Apex A | `mycodespace.ai` → `34.120.230.82` |
| www CNAME | `www.mycodespace.ai` → `mycodespace.ai.` |

Authenticate with `gcloud auth login`, then run from this directory:

```bash
npm run deploy -- plan      # Prints targets; no cloud changes
npm run deploy -- update    # Builds and synchronizes this site's bucket
```

Updates delete unmatched files in the dedicated bucket. HTML is cached for five
minutes; hashed Astro assets are cached for a year. If needed, invalidate only
hosts `mycodespace.ai` and `www.mycodespace.ai` on `chessclub-site-url-map`.

For initial setup or to reapply missing resources:

```bash
npm run deploy -- provision
```

Provision checks the existing load balancer and conflicting DNS records, creates
the dedicated public bucket/backend, builds and uploads the site, appends a
certificate covering both names, adds an exact host rule, and creates/updates
only the apex A and www CNAME. It preserves existing certificates, default
backend, other host rules, and unrelated DNS records. It does not change
project-wide organization policies or configure HTTP redirects. GCP billing
applies. Existing targets can be overridden with environment variables.

Certificate activation and routing propagation may take time. Verify both HTTPS
hosts and the original chess site after provisioning. DevCapsule remains on its
existing independent GitHub Pages CNAME.

## Contact section

The introduction places the contact invitation to the right of the headline, lead and
explanation on wide screens. Text can use the full width below the card;
narrower screens stack the text and invitation in reading order.
The contact section includes Costin’s GitHub and LinkedIn profiles and an email
image at `public/contact-email.svg`. The SVG uses glyph outlines rather than
text, with a spoken-form alt description for accessibility and no mailto link.
This reduces trivial address scraping; it does not prevent OCR. To change the
address, regenerate the outlines and update the alt description together.
The owner approved and deployed the contact update on 2026-11-01.

The owner-supplied chess photo lives at `src/assets/costin-cozianu-chess.jpg`
(originally `maxresdefault.jpg`). Astro generates cropped 320/640px WebP variants retaining Costin on the left and the
foreground chessboard; an asymmetric egg-shaped CSS mask frames the scene. The chess partner on the right is excluded
from the generated images. The original source remains in src/assets for editing.
