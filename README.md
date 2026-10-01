# Teaching materials for novices

## Structure Overview

Top-level files and directories you'll commonly interact with:

- `_quarto.yml` — Site configuration (title, navigation, output settings, theme). Update this to change the site title, navigation order, or basic site settings. We already have a multitude of presets in place here, but feel free to look at Quarto's documentation for further options.
- `index.qmd` — The site homepage content i.e. the landing page when someone opens the link to the tutorial. This should generally be an overview of the tutorial + necessary software information.
- `about.qmd` — The about page. Its main role is to contain License, Citation, and Contributor information.
- `CITATION.cff` — Citation metadata for the project (authors, affiliations, ORCID, etc.). See the official [CITATION.cff](https://citation-file-format.github.io/) documentation, or send an OSC member a message if it's unclear how to fill this in.
    - Note: you can also spot-check whether this is valid in R by running `install.packages("cffr"); cffr::cff_validate()`.
- `LICENSE.md` and `LICENSE-CODE.md` — License text for content and code respectively. We use CC-BY-SA 4.0 and CC0 1.0 Universal for authored content and code, respectively.
- `matomo-analytics.html` — Analytics snippet (managed by OSC staff; do not edit unless instructed).
- `assets/` — Images, downloads, CSS, bibliography, and other static files used by the site.
- `footer/` — Footer HTML, styling, and the imprint/privacy/accessibility pages.
- `open-research-principles/`, `open-research-tools/`, `open-materials/` — Topic folders containing `.qmd` pages for each section of the materials.
- `_site/` — Generated site files (output). You normally do not edit this folder directly — it's produced when you build the site.
- `.filenameignore` — Patterns ignored by the automated filename check workflow. Add paths here if the workflow flags files that should be skipped.
- `.gitignore` — Files and directories Git should ignore (e.g., history files, temporary R output). Edit if your project generates new temporary files.

Styling and branding (logo, colours, typography) are provided by the [`lmu-osc/tutorial-template`](https://github.com/lmu-osc/tutorial-template) Quarto extension in `_extensions/`, so there is no project-level SCSS or `styles.css` to maintain. Do not hand-edit files under `_extensions/`; the `Update Tutorial Template Extension` workflow keeps them current.

If you want to change what appears in the site's navigation, edit the `sidebar:` and `navbar:` sections in `_quarto.yml`.

## Running Actions (for non-technical contributors)

This repository has several automations in place to help ensure consistency across our repositories, namely a citation file checker, a filename checker, an automation for publishing the site, and a code style formatter. You can see details at `.github/workflows/README.md` if interested, but it's not required to know these details by any means.

- If you need to run a repository workflow (for example to re-render the site), open this repository on GitHub and click the **Actions** tab.
- Select the workflow you want (examples: "Render Quarto Site", "Check CITATION.cff", "Filename Checks", "Tidyverse Style Formatting").
- Click **Run workflow**, and then select the branch you want to test a workflow on from the "Branch:" dropdown. Then click **Run workflow** again to start it.
- After the workflow starts, you can monitor progress on the same page and inspect step logs if something fails. If you are unsure what to do after a failure, open a GitHub issue and paste the error or screenshot.
- If you do not see the **Run workflow** button, you can still make changes by editing files and pushing them to GitHub; the workflows that trigger on `push` will run automatically.

## Conventions and tips

- File names: lowercase and kebab-case (e.g. `my-topic/my-page.qmd`).
- Content: use plain text and simple Markdown/Quarto; avoid embedding complex web widgets unless needed.
- Collaboration: edit content on GitHub using branches and pull requests so teammates can review changes.
