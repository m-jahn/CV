# CV - curriculum vitae - Michael Jahn

Simple repository for maintaining an up-to-date, lean, and public version of my CV.

### Content

- `docs/` - rendered HTML of my data science [portfolio](https://m-jahn.github.io/CV/portfolio.html)
- `figures/` - source figures for CV
- `pdf/` - rendered PDF of the CV
- `portfolio/` - R notebook with recent statistics on publications, citations, and projects
- `tex/` - the laTex source document(s) for the CV, including styles for `modernCV` theme

### Installation and build

The LaTex installation and `modernCV` theme require the following packages

```bash
sudo apt install texlive-base texlive-binaries texlive-fonts-recommended texlive-latex-base texlive-latex-recommended texlive-latex-extra
```

I recommend Rstudio or Texmaker as simple IDEs.

### Data science 'portfolio'

The repo contains an R notebook (source: `portfolio/portfolio.Rmd`) that automatically retrieves citation and profile data from [Google scholar](https://scholar.google.com/) and [Github](https://github.com/). Retrieval is performed using R packages [scholar](https://github.com/jkeirstead/scholar) and [gh](https://github.com/r-lib/gh).
A rendered HTML of the portfolio is available [here](https://m-jahn.github.io/CV/portfolio.html).
