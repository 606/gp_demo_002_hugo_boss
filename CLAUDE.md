# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Hugo static site generator project configured for automatic deployment to GitHub Pages.

## Build Commands

```bash
# Local development server
hugo server

# Production build (matches CI)
hugo --minify

# Build with specific base URL
hugo --minify --baseURL "https://example.com/"
```

## Deployment

Automated via GitHub Actions on push to `main` branch. The workflow:
1. Installs Hugo Extended 0.128.0 and Dart Sass
2. Installs Node.js dependencies if package-lock.json exists
3. Builds with `hugo --minify` in production environment
4. Deploys to GitHub Pages

## Architecture

This is a skeleton Hugo project. Standard Hugo directory structure should be used:

- `content/` - Markdown content files
- `layouts/` - HTML templates
- `static/` - Static assets (images, CSS, JS)
- `themes/` - Hugo themes (as git submodules)
- `hugo.toml` - Site configuration (needs to be created)

Themes are loaded as git submodules (checkout uses `submodules: recursive`).
