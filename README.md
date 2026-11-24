# nicholasnapolio.com: static version (no Squarespace)

Plain HTML + CSS. No build step, no database, no monthly fee. Any free static host can serve this folder as is.

## What's here
- `index.html` (Bio / C.V.), `research.html`, `teaching.html`, `organizing.html`: the same content as the Squarespace pages, word for word.
- `style.css`: all of the styling.
- `s/`: the PDFs and CSVs, at the same `/s/<file>` paths Squarespace used, so old links to your papers and C.V. keep working.
- `images/`: the headshot and the ORCID icon.
- `new-index-1.html`: redirects the old Squarespace "Organizing" URL to `organizing.html`.
- `CNAME`: tells GitHub Pages to serve this at www.nicholasnapolio.com.

## Editing
- Open the `.html` file in any text editor and change the text. Each publication is one `<p>...</p>` line.
- To post a new PDF, put it in `s/` and link it as `s/filename.pdf`.
- To update the C.V., replace `s/Napolio-CV.pdf` and keep the same file name.

## Hosting (free). Pick one
**Netlify Drop (easiest, no git):** go to app.netlify.com/drop and drag this folder onto the page. To update the site later, drag the folder again.
**Cloudflare Pages:** create a Pages project with "Direct upload" and upload this folder.
**GitHub Pages:** create a public repo, push this folder to it, then go to Settings → Pages → Deploy from branch (main, root).

## Pointing the domain
The domain is registered through Squarespace Domains (Tucows); it renews 2027-09-12.
1. On the new host, add `www.nicholasnapolio.com` and `nicholasnapolio.com` as custom domains. The host will show you the DNS records it needs.
2. In Squarespace: Domains → nicholasnapolio.com → DNS settings. Remove the Squarespace website records and add the host's records:
   - GitHub Pages: `CNAME www → <username>.github.io`, plus A records for the apex domain: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153.
   - Netlify / Cloudflare: use the records their dashboard gives you.
3. Once the new site loads on your domain, cancel the Squarespace **website** subscription and keep the **domain**. Or transfer the domain to Cloudflare Registrar or Porkbun, which are usually cheaper.

Preview locally: `python3 -m http.server` in this folder, then open http://127.0.0.1:8000.
