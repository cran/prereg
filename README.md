prereg: R Markdown Templates for Preregistrations of Scientific Studies
================

[![CRAN/METACRAN](https://img.shields.io/cran/v/prereg?label=CRAN&logo=r)](https://cran.r-project.org/package=prereg)
[![Download
counter](https://cranlogs.r-pkg.org/badges/prereg)](https://cran.r-project.org/package=prereg)
[![Project Status: Active - The project has reached a stable, usable
state and is being actively
developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org)
![GitHub last
commit](https://img.shields.io/github/last-commit/crsh/prereg/master?label=Last%20commit&logo=github&logoColor=%23FFF)
![Travis build
status](https://img.shields.io/travis/crsh/prereg?label=Build&logo=travis-ci&logoColor=%23FFF)
[![GitHub bug
issues](https://img.shields.io/github/issues/crsh/prereg/bug?label=Bugs&logo=github&logoColor=%23FFF)](https://github.com/crsh/prereg/issues?q=is%3Aopen+is%3Aissue+label%3Abug)

`prereg` provides [R Markdown](https://rmarkdown.rstudio.com/) templates
that facilitates authoring preregistrations of scientific studies in PDF
format.

If you experience any problems or have suggestions for improvements,
please [open an issue](https://github.com/crsh/prereg/issues).

## Setup

### Requirements

To use R Markdown and `prereg` you need the following software on your
computer:

  - [R](https://www.r-project.org/) (2.11.1 or later)
  - [RStudio](https://rstudio.com/) (0.99.441 or later) is optional; if
    you don’t use RStudio, you need to install
    [pandoc](https://pandoc.org/) using the [instructions for your
    operating system](https://pandoc.org/installing.html)
  - A [TeX](https://de.wikipedia.org/wiki/TeX) distribution (2013 or
    later; e.g., [MikTeX](https://miktex.org/) for Windows,
    [MacTeX](https://tug.org/mactex/) for Mac, obviously, or [TeX
    Live](https://www.tug.org/texlive/) for Linux)
      - If you are running **Windows**, use MikTex if possible.
        Currently, pandoc and the Windows version of Tex Live [don’t
        seem to like each
        other](https://github.com/rstudio/rmarkdown/issues/6). Make sure
        you install the *complete*—not the basic—version.

### Install prereg

You can install the stable version of `prereg` from CRAN

``` r
install.packages("prereg")
```

or the development version from this GitHub repository (you may have to
install the `devtools` package first).

``` r
install.packages("devtools")
devtools::install_github("crsh/prereg")
```

### Create a preregistration document

Once you have installed the `prereg` you can select the templates when
creating a new R Markdown file through the RStudio menus.

![](tools/images/template_selection.png)

#### Example

`prereg` produces a clean form-like document.

![](tools/images/prereg_page1.png) ![](tools/images/prereg_page2.png)

The template file contains comments that provide further details on how
to fill in the form but are invisible in the final PDF document.

![](tools/images/prereg_rmd.png)

#### Using prereg without RStudio

If you want to use `prereg` without RStudio you can use the
`rmarkdown::render` function to create preregistration documents:

``` r
# Create new COS preregistration challenge R Markdown file
rmarkdown::draft(
  "my_preregistration.Rmd"
  , "cos_prereg"
  , package = "prereg"
  , create_dir = FALSE
  , edit = FALSE
)

# Render document
rmarkdown::render("my_preregistration.Rmd")
```

## Uploading your preregistration

After knitting your preregistration to a PDF file using this package,
you may upload this protocol to a trustworthy repository to complete
your preregistration. Possible repositories for this are:

  - [Preregistration in Psychology](https://prereg-psych.org/): A
    preregistration platform provided by the Leibniz Institute for
    Psychology (ZPID) which focuses on psychological research
  - [Open Science Framework](https://osf.io/prereg/): An
    interdisciplinary platform provided by the Center for Open Science
    where preregistrations as well as other materials and data can be
    uploaded

## Acknowledgments

The templates for the preregistrations were developed by the [Center for
Open Science](https://www.cos.io/initiatives/prereg/),
[AsPredicted.org](https://aspredicted.org/), Anna Elisabeth van ’t Veer
and Roger Giner-Sorolla, and a task force composed of members of the
American Psychological Association (APA), the British Psychological
Society (BPS), the German Psychological Society (DGPs), the Center for
Open Science (cos), and the Leibniz Institute for Psychology (ZPID). I’m
thankful for their permission to use their material in this package.

## Package dependencies

![](tools/images/unnamed-chunk-1-1.png)<!-- -->

# References

Brandt, M. J., IJzerman, H., Dijksterhuis, A., Farach, F. J., Geller,
J., Giner-Sorolla, R., … van ’t Veer, A. (2014). The Replication Recipe:
What makes for a convincing replication? *Journal of Experimental Social
Psychology*, 50, 217–224. doi:
[10.1016/j.jesp.2013.10.005](https://doi.org/10.1016/j.jesp.2013.10.005)

van ’t Veer, A. E., & Giner-Sorolla, R. (2016). Pre-registration in
social psychology—A discussion and suggested template. *Journal of
Experimental Social Psychology*, 67, 2–12. doi:
[10.1016/j.jesp.2016.03.004](https://doi.org/10.1016/j.jesp.2016.03.004)
