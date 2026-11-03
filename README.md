# Niksera Technologies website

Static site for niksera.com. No build step: everything Cloudflare serves lives in `public/`.

## Edit content
Open `public/index.html` and change the text. The contact form posts to Salesforce Web-to-Lead (org ID `00Dfj00000lurRa`).

## Deploy on Cloudflare
The project deploys as a Cloudflare Worker with static assets (see `wrangler.jsonc`). Connect the GitHub repo in Workers & Pages with the deploy command `npx wrangler deploy` and no build command. Every push to `main` redeploys.

## Custom domain
Worker > Settings > Domains & Routes > Add custom domain: `niksera.com`, then `www.niksera.com`. HTTPS is automatic.
Redirect www to the apex: Cloudflare Dashboard > Rules > Redirect Rules (a `_redirects` file cannot hold absolute URLs on Workers).

## Analytics (optional)
Cloudflare Dashboard > Web Analytics > add `niksera.com`, then enable automatic setup for the Pages project.

## Notes
- `public/_headers` sets security headers. If you add scripts, fonts or embeds from new hosts, update the Content-Security-Policy there.
- Placeholders still to replace: address, phone, public email, logo file.
