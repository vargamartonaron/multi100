
# multi100

The goal of multi100 is to store the data preprocessing and analysis
codes for the Multi 100 study.

## Folder structure

The `data/` folder contains all the datafiles that are needed to
reproduce the results of the project. The datafiles that contains
personal information are not shared (e.g. source files with email
addresses).

The `analysis/` folder contains all the analyses files in quarto
documents. Within this folder you can find the following files:

- `multi100_source_raw.qmd` file contains the code necessary for the
  transformation of the source data (the datafile downloaded directly
  from Google Forms as is) to the raw datafile (datafile with standard
  names). We also made sure that the raw datafiles do not contain any
  the email adresses of analysts and peer evaluators.
- `multi100_raw_processed.Rmd` file contains the code that cleans the
  dataset and transforms is into a tidy format ready for the analysis.
  We also merge the analyst responses for task 1 and task 2 into one
  datafile and store the peer evaluations in a separate file.
- `multi100_analysis.Rmd` file contains the code for the figure creation
  and the analysis.

The `figures/` folder contains all the figures that are created in the
`multi100_analysis.Rmd` file.

## Reproducibility and Software Environment

This project uses the {renv} package to manage R package dependencies,
ensuring a reproducible environment. Below are the details regarding
software dependencies, tested versions, and system requirements.

### 1. Software Dependencies and Operating System

All R package dependencies, including version numbers, are captured in
the `renv.lock` file. This file allows you to recreate the exact
software environment used for the analyses.

- Operating System Tested On:
  - **Primary OS:** Windows 11 64bit, Linux Mint 20.3 64bit
  - **R Version:** 4.3.0, 4.4.2
  - **Package Versions:** As specified in `renv.lock`.

### 2. Required Hardware For Smooth Operation

- **Standard Hardware:** The analysis can be run on standard desktop or
  laptop computers with at least:
- **RAM:** Minimum 4GB
- **Processor:** modern multi-core CPU
- **Non-Standard Hardware:** None required.

## How to Reproduce the Analysis Using `{renv}`

1.  Install R and RStudio (optional):

- [Download R](https://cran.r-project.org/bin/windows/base/)
- [Download RStudio](https://posit.co/download/rstudio-desktop/) (if
  preferred)

2.  Install {renv} (if not already installed):

``` r
install.packages("renv")
```

3.  Clone or Download This Project:

- Clone via Git:

<!-- -->

    git clone https://github.com/marton-balazs-kovacs/multi100.git

- Or download the ZIP file and extract it.

4.  Restore the Project Environment: Open the project in R (or RStudio)
    and run:

``` r
renv::restore()
```

This command will:

- Install the exact versions of all packages listed in `renv.lock`.
- Ensure compatibility with the tested environment.
- Installing the `renv` environment takes about 10 minutes on an average
  computer with Windows 11 64bit.

5.  Run the Analysis: Execute the main analysis script:

``` r
rmarkdown::render("analysis/multi100_results.qmd")
```

This command will generate the main manuscript and save each figure
separately. Generating the main manuscript takes about 7 minutes on an
average computer.
