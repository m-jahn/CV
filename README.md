# CV - curriculum vitae - Michael Jahn

[![Build portfolio](https://github.com/m-jahn/CV/actions/workflows/build_portfolio.yml/badge.svg)](https://github.com/m-jahn/CV/actions/workflows/build_portfolio.yml)
[![pages-build-deployment](https://github.com/m-jahn/CV/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/m-jahn/CV/actions/workflows/pages/pages-build-deployment)
![GitHub last commit](https://img.shields.io/github/last-commit/m-jahn/CV/main)

Repository for maintaining an up-to-date, lean, and public version of my CV.

### Content

- `docs/` - rendered HTML page of my data science [portfolio](https://m-jahn.github.io/CV/portfolio.html)
- `figures/` - source figures for CV
- `pdf/` - rendered PDF of the CV
- `portfolio/` - R notebook with recent statistics on publications, citations, and projects
- `tex/` - the laTex source document(s) for the CV, including styles for `modernCV` theme

### Installation and build

The LaTex installation and `modernCV` theme require the following packages.

```bash
sudo apt install
  texlive-latex-base
  texlive-latex-recommended
  texlive-latex-extra
  texlive-fonts-recommended
  texlive-fonts-extra
  cm-super
```

Install additional packages using `tlmgr`.

```bash
tlmgr install pdflatex
```

Render document using [pixi](https://pixi.prefix.dev/) tasks.

```bash
pixi run make-cv
```

### Personal (or confidential) information

Personal contact details (address, phone, email, photo) are kept in a separate file `tex/personalinfo.tex` which is not part of this repository (listed in `.gitignore`). In order to use the CV, create a simple `tex/personalinfo.tex` file and add your private information like this:

```latex
\newcommand{\addressline}{Your Street Address}
\newcommand{\addresspostal}{Your Postal Code City}
\newcommand{\addresscountry}{Your Country}
\newcommand{\mymobile}{Your Phone Number}
\newcommand{\myemail}{your.email@example.com}
\newcommand{\photopath}{../figures/profile.png}
\newcommand{\photosize}{0.25\textwidth}
```

### Data science portfolio

The repo contains an R notebook (source: `portfolio/portfolio.Rmd`) that automatically retrieves citation and profile data from [Google Scholar](https://scholar.google.com/) and [Github](https://github.com/).
Retrieval is performed using R packages [scholar](https://github.com/jkeirstead/scholar) and [gh](https://github.com/r-lib/gh).
A rendered HTML of the portfolio is available [here](https://m-jahn.github.io/CV/portfolio.html).

The portfolio can be built using a pixi task.

```bash
pixi run make-portfolio
```

The pixi task is automatically executed once a week and commits the updated portfolio to the `docs/` folder, which is then rendered by GitHub as a [static page](https://m-jahn.github.io/CV/portfolio.html).
