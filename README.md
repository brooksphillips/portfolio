# Brooks Phillips — Financial Modeling Portfolio

A single-page site for GitHub Pages showcasing financial models (LBO, DCF, three-statement, real estate, and financial strategy analysis) with downloadable Excel models and Word write-ups.

## What's in here

```
index.html                          the whole site (one page)
styles.css                          all styling
robots.txt                          keeps the site out of Google/Bing search results
assets/
  resume/Brooks_Phillips_Resume.pdf the résumé linked from the top button and footer
  models/                           the .xlsx models, one per card (BMS has two)
  analysis/                         the .docx write-ups, one per card (BMS has two)
```

## Publishing it on GitHub Pages

1. Push every file in this folder to the `brooksphillips/portfolio` repo, **keeping the folder structure** (`assets/resume/`, `assets/models/`, and `assets/analysis/` all need to stay intact — `index.html` links to those exact paths).
2. If you're replacing the old site wholesale, delete the old `assets/models/BMC_LBO_Model_with_DCF.xlsx` — it's been superseded by `assets/models/BMC_LBO_DCF.xlsx`.
3. Confirm **Settings → Pages** is still set to deploy from the `main` branch, `/ (root)` folder. No change needed if it was already configured this way.
4. GitHub redeploys automatically within a minute or two of the push. The site stays at `https://brooksphillips.github.io/portfolio/`.

## Staying out of search results

`robots.txt` and a `noindex` meta tag in `index.html` are already in place, so search engines won't index the page — but the direct link still works for anyone you send it to.

## Adding or updating a project

Each project is one `<article class="card">` block inside `index.html`, in the "Selected work" section.

- **Standard project (one model + one write-up):** drop the `.xlsx` into `assets/models/` and the `.docx` into `assets/analysis/`, then copy an existing card's markup and update the kind, title, summary, and the two `href`s in its single `.download-row`.
- **Project with multiple models (like BMS):** add one `.download-row` per model/write-up pair, each with a short `<span class="download-row-label">` (e.g. "Operational", "Cash flow") in front of the two links.
- **Turning the placeholder into a real project:** copy the pattern above into the `card-placeholder` article, remove the `card-placeholder` class, and add a `status status-complete` (or `status-progress`) span next to `card-kind`.
- Bump the `<span class="count">` number in the "Selected work" heading to match how many completed models are shown (the placeholder box isn't counted).

Commit and push — GitHub Pages redeploys automatically within a minute or two.

## Updating your résumé

Replace `assets/resume/Brooks_Phillips_Resume.pdf` with a new file of the **same name** and it updates everywhere it's linked (top button + footer) with no other changes needed.
