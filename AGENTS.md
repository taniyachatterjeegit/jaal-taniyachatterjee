# Base44 Dev Environment

## What this project is
A single-page static site (`index.html`) for the "Jaal" web series — pure HTML/CSS/JS with a `screenshots/` folder of images. No backend, no build step, no package manager, no external credentials.

## How it runs
Served by `nginx:alpine` via `docker-compose.base44.yml` on host port 3000. The repo root is bind-mounted read-only into the container, so edits to `index.html` (or images) appear on a browser refresh with no rebuild.

## Verify it works
- `docker compose -f docker-compose.base44.yml up -d --build`
- `curl -sf http://localhost:3000/` returns the HTML page.
- The page loads 32 screenshot images from `screenshots/` and embeds a YouTube preview.
