# variadicgroup.com

The one-page site for Variadic Group. Plain HTML and CSS in `public/`: no build step, no
JavaScript, no trackers, no third-party requests. The typefaces (Funnel and JetBrains Mono) are
self-hosted under the SIL Open Font License; their licenses are in `public/fonts/`.

## Hosting

Cloudflare Workers static assets, deployed by Workers Builds on every push to `main`.
`wrangler.jsonc` names the Worker, serves `./public`, uses `public/404.html` for missing pages, and
attaches `variadicgroup.com` and `www.variadicgroup.com`. `public/_headers` sets the security
headers; the content security policy allows nothing but the site's own CSS, fonts and images.

Preview locally: `cd public && python3 -m http.server 8080`, then open http://localhost:8080.

## Content

- The thesis, the portfolio and a contact address. Every claim is true as written.
- The portfolio changes when a product launches: add its card to `#portfolio` and move "In
  selection" to the next slot.
- `public/og.png` is the link preview (1200×630); re-render it if the headline changes.
