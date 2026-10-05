# AGENTS.md

Portfolio site for Rishang Bhavsar, served by GitHub Pages at https://rishang.github.io/ from the `main` branch (no build step).

## Files

- `index.html`: the portfolio page. Single file, inline CSS and JS, no framework.
- `llms.txt`: plain-text summary of the same portfolio for LLMs, following https://llmstxt.org.
- `.nojekyll`: keeps GitHub Pages from running Jekyll. Don't delete it.

## Keep `index.html` and `llms.txt` in sync

They describe the same person, so any content change to one must be made to the other in the same commit. Content means facts: roles, dates, results, numbers, projects, talks, certifications, skills, contact details, links.

Section mapping:

| `index.html` | `llms.txt` |
|---|---|
| Hero lede, proof line, `rishang.yaml` manifest | Blockquote summary and the paragraph below it |
| `#impact` Results | "Key results" list |
| `#oss` Projects (featured and More tools) | `## Open source projects` |
| `#stack` Stack and tooling | `## Optional` Skills line |
| `#work` Experience | `## Experience` |
| `#talks` Talks | `## Talks` |
| `#creds` Certifications and education | `## Optional` |
| `#contact` and header links | Contact line and `## Profile` |

Rules:

- Adding, removing or renaming a project, job, talk or certification: update both files.
- Changing a number (downloads, stars, cost cuts, years): update both. The page has baked-in fallback values next to its `data-live` attributes; update those too, and use the same rounded figure in `llms.txt`.
- Years of experience are computed in `index.html` from April 2021. In `llms.txt`, write "5+ years" style text and bump it when the page's value changes.
- Visual or layout-only changes (CSS, markup, animation) need no `llms.txt` change.
- Voice differs on purpose: the page is first person ("I built..."), `llms.txt` is third person ("he automated..."). Keep the facts identical, not the wording.

## Facts

- Every claim must trace to the CV, a public repo README, a registry, or a public event page. Don't invent scope, team sizes or numbers. If a number is unknown, leave it out and ask.
- Download counts come from shields.io JSON endpoints (`img.shields.io/terraform/module/dt/...`, `pepy/dt/...`, `github/stars/...`, `docker/pulls/...`). Helm charts have no public download count, so don't show one.

## Writing style

- No em dashes. Use commas, colons, periods or parentheses.
- Contractions, plain verbs, sentence case. Result first, then the number, then how.
- No hype words ("passionate", "blazing", "rockstar").

## Before committing

Check that every project linked on the page is also in `llms.txt`. No output means in sync:

```bash
diff <(rg -o 'github\.com/(Rishang|ss-rishang)/[A-Za-z0-9._-]+' index.html | sort -u) \
     <(rg -o 'github\.com/(Rishang|ss-rishang)/[A-Za-z0-9._-]+' llms.txt | sort -u)
```

Then reread both files side by side using the section mapping above. The diff only catches missing project links, not changed facts.

To preview, open `index.html` in a browser. Check it at desktop and phone widths (390px) and in dark mode.
