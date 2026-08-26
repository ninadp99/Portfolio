# Handoff: Deploy Portfolio Site to GitHub Pages

## Task
Deploy the static site in this folder to the `ninadp99/Portfolio` GitHub repository (branch `main`), replacing the old build output. GitHub Pages is **already enabled** on this repo (source: "Deploy from a branch", branch `main`, folder `/root`), so once the new files are committed to `main`, the existing Pages deployment will pick them up automatically — no Pages configuration changes needed.

## What's in this folder
Everything is at the repo root level already — copy it in as-is:
- `index.html` — the site's home page (entry point GitHub Pages will serve)
- `Home.dc.html` — identical copy of index.html, kept so internal links using this filename still resolve
- `project-amex-platform.dc.html`, `project-agentic-search.dc.html`, `project-genai-pilots.dc.html`, `project-athena-ai.dc.html`, `project-ndc-airline.dc.html` — five project case-study pages
- `CaseStudy.dc.html` — shared case-study layout imported by the five project pages
- `support.js` — runtime script required by all the `.dc.html` files (pure client-side, no build step, no backend calls needed for rendering)
- `assets/` — avatar image, certificate images, and the resume PDF

These are plain static files — open `index.html` directly in a browser and everything should render, including navigation between pages and the dark/light toggle.

## Steps for Claude Code
1. In the `ninadp99/Portfolio` repo, on branch `main`, **delete** the old build output at the repo root: `index.html`, `assets/index-*.js`, `assets/index-*.css`, and the old `.gitignore` if present (these were leftovers from a previous Vite build and are no longer used).
2. Copy every file/folder from this handoff bundle into the repo root, preserving the folder structure (`assets/` merges with — and should end up only containing — the new asset files listed above).
3. Commit and push to `main`.
4. Confirm the deploy: visit `https://ninadp99.github.io/Portfolio/` after the Pages build finishes (usually under 2 minutes) and check that the homepage, project pages, and certifications section load without console errors.

## Notes
- No `npm install` / build step is required — these files run directly as static HTML/JS.
- If the repo's Pages settings ever get reset, they should be: Settings → Pages → Source: "Deploy from a branch" → Branch: `main` → Folder: `/ (root)`.
