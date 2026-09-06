# Campus to Career

A browser-based presentation. Edit `tech-career-journey.html`; `index.html` opens it automatically when someone visits the site.

## Publish on GitHub Pages

1. Push these files to the `main` branch of the `campus-to-career` repository.
2. In the repository, open **Settings → Pages**.
3. Select **Deploy from a branch**, then **main** and **/(root)**, and save.
4. Wait for the Pages deployment to finish. Open the site URL shown in Settings.

The `.nojekyll` file lets GitHub serve the HTML directly. No build command or dependencies are needed.

## Connect a Cloudflare domain

1. In **GitHub repository → Settings → Pages → Custom domain**, enter the full domain or subdomain you own and save it before changing DNS.
2. In **Cloudflare → your domain → DNS → Records**, configure the chosen hostname:
   - For a subdomain such as `career.example.com`, add a **CNAME** with name `career` and target `YOUR_GITHUB_USERNAME.github.io` (no protocol or repository path).
   - For the root domain such as `example.com`, add four **A** records with name `@`, one for each address: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`.
3. Use **DNS only** for these records so requests go directly to GitHub Pages. Review any existing records for that hostname before replacing them.
4. After GitHub's DNS check and certificate provisioning finish, enable **Enforce HTTPS** in Pages settings.
5. Saving a custom domain in GitHub creates a `CNAME` file in this branch. Pull that commit locally before your next push.

References: [GitHub Pages publishing](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site), [GitHub custom domains](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site), [Cloudflare DNS records](https://developers.cloudflare.com/dns/manage-dns-records/how-to/create-dns-records/).
