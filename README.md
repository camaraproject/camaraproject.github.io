# camaraproject.github.io

Repository for CAMARA GitHub Pages at https://camaraproject.github.io

## Site Structure

| Path | Source Directory | Description |
|------|------------------|-------------|
| `/` | `site-root/` | Landing page with links to tools |
| `/releases/` | `releases/` | Release viewers for CAMARA API meta-releases |
| `/swagger-ui/` | `swagger-ui/` | Display CAMARA API definitions in human-readable form |

## How Deployment Works

This site uses **explicit deployment** via GitHub Actions. Content changes are not automatically deployed on push.

The [pages-deploy.yml](.github/workflows/pages-deploy.yml) workflow:
1. Composes the full site from source directories into `_site/`
2. Deploys the complete site to GitHub Pages

This ensures deployments are intentional and traceable.

### Automated Deployments

**`/releases/`** - Deployed automatically by [project-administration](https://github.com/camaraproject/project-administration) when release viewer content is updated. The workflow pushes content to `releases/` and triggers `pages-deploy.yml`.

Note: `releases/` will be empty until the first automated deployment from project-administration.

### Manual Deployments

**`/swagger-ui/`** and **landing page** - After committing changes, manually trigger the "Deploy to GitHub Pages" workflow from the Actions tab.

## Repository Layout

```
camaraproject.github.io/
├── site-root/
│   └── index.html          # Landing page source
├── releases/               # Release viewer content (automated)
├── swagger-ui/             # Swagger UI tool
└── .github/workflows/
    └── pages-deploy.yml    # Deployment workflow
```
