# Al-Hira Public School website + admin panel

Static site (index.html) + Decap CMS admin at /admin. Staff log in with GitHub, edit content, press Publish.
That commits content.json and uploads/ to your repo, and Netlify redeploys automatically.

## Deploy (about 15 minutes)
1. Create a GitHub repo, upload everything in this folder.
2. Edit admin/config.yml: set `repo:` and both URLs. Edit robots.txt and sitemap.xml with your domain.
3. Netlify: Add new site > Import from Git > pick the repo (no build command, publish directory ".").
4. Netlify: Site configuration > Access & security > OAuth > install the GitHub provider (needs a GitHub OAuth app; Netlify guides you).
5. Open https://YOUR-SITE.netlify.app/admin and log in. Only GitHub users with write access to the repo can edit.
6. Remove `local_backend: true` from config.yml before going live.

## Local test
npx decap-server   (then serve this folder, e.g. npx serve, and open /admin)

## Notes
- Forms still open WhatsApp; there is no server to store enquiries. For stored enquiries add a form service (Netlify Forms, Formspree).
- Pages use #/hash routes, so search engines mostly see only the home page. For strong local SEO, move to Next.js (the content.json structure carries over).
- Student names and photos: publish only with guardian consent.
