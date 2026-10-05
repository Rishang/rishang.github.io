# rishang.github.io

Portfolio of Rishang Bhavsar, DevOps and platform engineer. Live at **https://rishang.github.io**.

## What's here

| File | Purpose |
|---|---|
| `index.html` | The portfolio page. One file with inline CSS and JS, no build step. |
| `llms.txt` | The same portfolio as plain text for LLMs ([llmstxt.org](https://llmstxt.org)). Served at [/llms.txt](https://rishang.github.io/llms.txt). |
| `AGENTS.md` | Rules for editing, including keeping `index.html` and `llms.txt` in sync. |
| `.nojekyll` | Tells GitHub Pages to serve files as-is. |

## Edit and preview

Open `index.html` in a browser. Check phone width (390px) and dark mode before pushing.

When you change a fact on the page (a project, number, job, talk or certification), make the same change in `llms.txt` in the same commit. See `AGENTS.md` for the section mapping and a quick sync check.

Download and star counts refresh live from [shields.io](https://shields.io) when the page loads. The numbers in the HTML are fallbacks if that request fails.

## Deploy

Push to `main`. GitHub Pages publishes it within a minute or so.
