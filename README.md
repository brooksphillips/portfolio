# Brooks Phillips — Financial Modeling Portfolio

A single-page site for GitHub Pages showcasing financial models (LBO, DCF, three-statement, credit memos, comps) with downloadable Excel files.

## What's in here

```
index.html                          the whole site (one page)
styles.css                          all styling
robots.txt                          keeps the site out of Google/Bing search results
assets/
  resume/Brooks_Phillips_Resume.pdf the résumé linked from the top button and footer
  models/
    BMC_LBO_Model_with_DCF.xlsx     the completed BMC LBO model, linked from its card
```

## Publishing it on GitHub Pages

1. Create a new repository on GitHub — for example `portfolio` (any name works). It can be public or private; GitHub Pages works either way on a free account as long as the repo is public, or with GitHub Pro/Team if private.
2. Upload every file in this folder to the repo, **keeping the folder structure** (the `assets/resume/` and `assets/models/` subfolders need to stay intact, since `index.html` links to those exact paths).
3. In the repo, go to **Settings → Pages**.
4. Under "Build and deployment," set **Source** to "Deploy from a branch," pick the `main` branch and the `/ (root)` folder, then save.
5. GitHub will publish the site at:
   ```
   https://brooksphillips.github.io/<repo-name>/
   ```
   (Replace `<repo-name>` with whatever you named the repository — e.g. `https://brooksphillips.github.io/portfolio/`.) It typically takes 1–2 minutes to go live after the first deploy.
6. Put that link on your resume/LinkedIn.

## Staying out of search results

`robots.txt` and a `noindex` meta tag in `index.html` are already in place, so search engines won't index the page — but the direct link still works for anyone you send it to. Note: GitHub Pages sites are still technically public — anyone who *has* the exact URL can view it, `noindex` only stops it from showing up in search results.

## Adding or updating a project

Each project is one `<article class="card">` block inside `index.html`, in the "Selected work" section. To turn a placeholder into a real project:

1. Drop the Excel file into `assets/models/` (give it a clear filename, e.g. `Company_DCF_Model.xlsx`).
2. In that card's block, update the company name, one-to-two sentence summary, and change the status span from `status-soon` ("Coming soon") to `status-complete` ("Complete") — or `status-progress` ("In progress") if it's not finished yet.
3. Replace the `<span class="pending-note">…</span>` line with a download link, matching the pattern used in the BMC card:
   ```html
   <a class="download-link" href="assets/models/Your_File.xlsx" download>
     <svg viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M8 1V11M8 11L4 7M8 11L12 7" stroke="currentColor" stroke-width="1.4" stroke-linecap="round" stroke-linejoin="round"/><path d="M2 13.5H14" stroke="currentColor" stroke-width="1.4" stroke-linecap="round"/></svg>
     Download model
   </a>
   <span class="filetype">.xlsx</span>
   ```
4. Commit and push — GitHub Pages redeploys automatically within a minute or two.

## Updating your résumé

Replace `assets/resume/Brooks_Phillips_Resume.pdf` with a new file of the **same name** and it updates everywhere it's linked (top button + footer) with no other changes needed.
