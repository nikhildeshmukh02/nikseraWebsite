# Niksera Technologies website

Static site for niksera.com. No build step: everything Cloudflare serves lives in `public/`.

## Edit content
Open `public/index.html` and change the text. The contact form posts to Salesforce Web-to-Lead (org ID `00Dfj00000lurRa`).

## Deploy on Cloudflare Pages
1. Push this repo to GitHub.
2. Cloudflare Dashboard > Workers & Pages > Create > Pages > Connect to Git, then pick `niksera-website`.
3. Framework preset: None. Build command: leave empty. Build output directory: `public`.
4. Save and Deploy. Every push to `main` redeploys automatically; pull requests get preview URLs.

## Custom domain
Pages project > Custom domains > Set up a domain > `niksera.com`, then add `www.niksera.com`. HTTPS is automatic. `public/_redirects` sends www to the apex domain.

## Analytics (optional)
Cloudflare Dashboard > Web Analytics > add `niksera.com`, then enable automatic setup for the Pages project.

## Notes
- `public/_headers` sets security headers. If you add scripts, fonts or embeds from new hosts, update the Content-Security-Policy there.
- Placeholders still to replace: address, phone, public email, logo file.
