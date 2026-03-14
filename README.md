# website

## GitHub Pages

The site is built from the **orbitist.com** directory only. A GitHub Actions workflow (`.github/workflows/deploy-pages.yml`) deploys that folder as the site root so the Pages URL serves the orbitist.com content at `/`.

**Setup:** In the repo on GitHub go to **Settings → Pages**. Under "Build and deployment", set **Source** to **GitHub Actions**. Pushes to `main` will run the workflow and deploy. If your default branch is not `main`, edit the workflow and change `branches: [main]` to your branch name.