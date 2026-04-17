# notify-docs

Documentation for the partner notification platform: onboarding, notification setup, authentication, and technical discovery flows.

## Browse locally

```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
mkdocs serve
```

Open the URL printed in the terminal (usually `http://127.0.0.1:8000/`).

## GitHub Pages (automatic)

The workflow [`.github/workflows/deploy-pages.yml`](.github/workflows/deploy-pages.yml) builds the site with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/) on every push to `main` (and on manual **Run workflow**).

1. In the GitHub repository, go to **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to **GitHub Actions** (not “Deploy from a branch”).
3. Edit [`mkdocs.yml`](mkdocs.yml): set `site_url` and `repo_url` / `repo_name` to match your site. For a **project site**, use `https://<owner>.github.io/<repo>/` including the trailing slash. For a **user or organization site** (`<user>.github.io` with no repo path), follow [GitHub Pages docs](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages#types-of-github-pages-sites) and adjust `site_url` accordingly.
4. Push to `main`. The **pages-build-deployment** / **Deploy documentation to GitHub Pages** run should publish the `site/` output.

## Layout

| Path | Purpose |
|------|---------|
| [`docs/`](docs/index.md) | Source Markdown for the published site |
| [`docs/technical-flows/`](docs/technical-flows/index.md) | Discovery flows: `.mmd` sources plus wrapper pages that render them |
| [`mkdocs.yml`](mkdocs.yml) | Site name, nav, theme, Mermaid / snippets |

Later steps can add an `docs/architecture/` area for AWS (EKS, Secrets Manager, Aurora PostgreSQL, event-driven design) without changing this layout.
