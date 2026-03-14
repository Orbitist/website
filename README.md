# website

## GitHub Pages

The site is built from the **orbitist.com** directory only. A GitHub Actions workflow (`.github/workflows/deploy-pages.yml`) deploys that folder as the site root so the Pages URL serves the orbitist.com content at `/`.

**Setup:** In the repo on GitHub go to **Settings → Pages**. Under "Build and deployment", set **Source** to **GitHub Actions**. Pushes to `main` will run the workflow and deploy. If your default branch is not `main`, edit the workflow and change `branches: [main]` to your branch name.

### Custom domain (orbitist.com)

1. **On GitHub:** In the repo go to **Settings → Pages**. Under "Custom domain", enter **orbitist.com** and click **Save**. Optionally enable **Enforce HTTPS** once the domain is working.

2. **At your DNS provider** (where orbitist.com is registered), add:

   **Apex (orbitist.com):**  
   - Either four **A** records for `@` pointing to:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - Or one **ALIAS** / **ANAME** record for `@` pointing to **`YOUR-GITHUB-USERNAME.github.io`** (if your DNS host supports it).

   **www (optional but recommended):**  
   - One **CNAME** record: name **www**, value **`YOUR-GITHUB-USERNAME.github.io`**.

   Replace `YOUR-GITHUB-USERNAME` with the GitHub user or org that owns the repo. For a **project** site (e.g. `username.github.io/orbitist-website`), the CNAME/ALIAS target is still `username.github.io` (no repo name).

3. **Wait for DNS** (up to 24–48 hours). GitHub will then issue an HTTPS certificate for orbitist.com. After that you can turn on **Enforce HTTPS** in Pages settings.