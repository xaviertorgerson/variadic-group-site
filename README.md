# variadicgroup.com

The public one-page site for Variadic Group LLC. Plain HTML and CSS in `public/`, no build step,
no JavaScript, no trackers, no third-party requests (the typefaces, Funnel and JetBrains Mono, are
self-hosted under the SIL Open Font License; licenses in `public/fonts/`).

## Hosting

Cloudflare Workers static assets (Cloudflare's recommended home for new static sites), deployed
by Workers Builds on every push to `main`. `wrangler.jsonc` names the Worker
(`variadic-group-site`), serves `./public`, uses `public/404.html` for missing pages, and attaches
the custom domains `variadicgroup.com` and `www.variadicgroup.com`. `public/_headers` sets the
security headers (a strict CSP: the page loads nothing but its own CSS, fonts and images).

Preview locally: `cd public && python3 -m http.server 8080`, then open http://localhost:8080.

## Rules for the content

- Public-facing only: the thesis, the portfolio and a contact. No internals (bank, vendors, stack,
  costs, team process detail) and no figure that needs regular upkeep.
- Every claim is true today. The portfolio is the one part that changes: when a product launches,
  its card goes into `#portfolio` (copy the Heirloom card; the next one becomes "Product 003 · In
  selection"). The company's new-product checklist includes this step.
- No fundraising ask, valuation or revenue figure until a securities lawyer has reviewed the page
  (decided 2026-10-27 in the private `variadic-group` repo).
- No home address, phone or personal email. The contact is `hello@variadicgroup.com`.
- `public/og.png` is the social preview (1200×630); re-render it if the headline changes.
