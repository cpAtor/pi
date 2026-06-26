# Architecture docs preview

This folder contains the architecture review deliverables added for PR preview and pre-merge discussion:

- `index.html` - landing page for the docs bundle
- `repo-architecture.html` - repository-derived architecture report with 12 Mermaid diagrams
- `conceptual-architecture.html` - conceptual/reference architecture report with 12 Mermaid diagrams

## Preview locally

Use any static file server so the Mermaid ESM module can load cleanly:

```bash
cd <repo-root>
python3 -m http.server 8000 --directory docs
```

Then open `http://127.0.0.1:8000/`.

## Preview from GitHub Actions

Pull requests trigger `.github/workflows/docs-preview.yml`, which uploads the full `docs/` directory as an artifact.

1. Open the PR workflow run.
2. Download the `docs-preview-pr-<number>` artifact.
3. Extract it and open `index.html` in a browser.

## Pages-compatible deploy path

If Pages is enabled with **Settings -> Pages -> Build and deployment -> GitHub Actions**, `.github/workflows/pages-docs.yml` can publish the same `docs/` directory:

- automatically on pushes to `main` when the docs site changes
- manually with `workflow_dispatch`
