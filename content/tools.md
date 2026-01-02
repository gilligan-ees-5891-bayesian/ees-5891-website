---
title: Tools
---

# Software Tools

This course will use R statistical analysis software. We will use several 
specialized Bayesian analysis packages written for R 

## Menu {#menu}

* [Installing tools](#installing "Tools to install on your computer")
  * [Installing {{< R_LOGO >}}](#installing-r "Installing R")
  * [Installing {{< RSTUDIO_LOGO >}}](#installing-rstudio "Installing RStudio")
  * [Installing R packages for Bayesian statistics](#installing-r-packages)
  * [Update: installing `cmdstanr` and additional tools](#installing-cmdstanr)
* [Optional tools](#optional-tools "Optional tools you may want to install")
  * [Installing the tinytex package](#installing-latex "Installing the tinytex package for making PDFs from RMarkdown")
  * [Installing git for software revision management](#installing-git "Installing Git for revision management")
* [Resources for learning more](#resources "Free online reading and videos about using R, RStudio, etc.")
  * [{{< R_LOGO >}} and {{< RSTUDIO_LOGO >}}](#r-resources "Learning more about R and RStudio")
  * [{{< GIT_LOGO >}} and {{% GITHUB %}} {{< GITHUB_LOGO >}}](#git-resources "Learning about using Git with R for software revision control")

## Installing Tools {#installing}

### Installing {{< R_LOGO >}} {#installing-r}

* Download R version 4.5.2 from [https://cran.rstudio.com/](https://cran.rstudio.com/)
  * **Windows:** 
    * Download and install the ["base distribution" of R 4.5.2](https://cran.rstudio.com/bin/windows/base/).
  * **MacOS:**
    * Download and install [R version 4.5.2](https://cran.rstudio.com/bin/macosx/)
  * **Linux:**
    * You should be able to install R from your Linux distribution's 
      package manager:
      * `sudo apt-get install r-base r-base-dev` for Debian or Ubuntu
      * `sudo yum install R` or `sudo dnf install git` for Fedora, 
        Red Hat, and related distributions.
      * If you are using Ubuntu, there are 
        [advanced instructions](https://cran.rstudio.com/bin/linux/ubuntu/fullREADME.html) 
        for configuring the package management system to use the very 
        latest versions of R and its associated packages at 
        <https://cran.rstudio.com/bin/linux/ubuntu/fullREADME.html>.
        This is optional and the default version of R should be fine for
        this class, as long as it is version 4.5 or higher.
* If you have a version of R older than 4.5, you should update it to 4.5
  or higher.

### Installing {{< RSTUDIO_LOGO >}} {#installing-rstudio}

RStudio is a free editing and software development environment that
makes it much easier to work with R. I strongly recommend that you 
install RStudio for this course.

* Go to the download page for the free desktop edition of 
  {{% RSTUDIO %}} at 
  [https://posit.co/download/rstudio-desktop/](https://posit.co/download/rstudio-desktop/ "Download RStudio") and
  download the installer for your operating system. Windows, MacOS, 
  and the Debian, Ubuntu, Fedora, RedHat, and openSUSE editions of
  Linux are all supported.
  
  There are other versions of {{% RSTUDIO %}} (an expensive professional 
  edition and a server edition). 
  You want the **free desktop edition**.
  As of January 2026, the latest version is RStudio Desktop version 
  2025.09.2+418 "Cucumberleaf Sunflower".
* Run the installer. 
* After the installer finishes running, run {{% RSTUDIO %}}.
  * When {{% RSTUDIO %}} starts up, the lower left part of the screen 
    should have a window that displays the R version, saying something 
    like this:
    
    ```
    R version 4.5.2 (2025-10-31 ucrt) -- "[Not] Part in a Rumble"    
    Copyright (C) 2025 The R Foundation for Statistical 
    Computing Platform: x86_64-w64-mingw32/x64
    
    R is free software and comes with ABSOLUTELY NO WARRANTY.
    You are welcome to redistribute it under certain conditions.
    Type 'license()' or 'licence()' for distribution details.
    
      Natural language support but running in an English locale
    
    R is a collaborative project with many contributors.
    Type 'contributors()' for more information and
    'citation()' on how to cite R or R packages in publications.
    
    Type 'demo()' for some demos, 'help()' for on-line help, or
    'help.start()' for an HTML browser interface to help.
    Type 'q()' to quit R.
    ```
    The details will be different depending on your operating system, 
    but if you see something like this, {{% RSTUDIO %}} correctly found 
    R on your computer.
  * Configuring RStudio for additional optional software. There are a 
    few other pieces of software that you may want to use this semester, 
    but these are not required.

    If have installed the Git revision control system or the 
    {{< LATEX_LOGO >}} typesetting software, you should configure 
    RStudio to use them:
  * If will use Git for software revision control with R, you should 
    open the "Tools" menu, and click on the "Global Options" choice.
    * Go to the "Git/SVN" tab and click "enable version control 
      interface for {{% RSTUDIO %}} projects". 
      If {{% RSTUDIO %}} can find the git program on your computer, 
      it will appear in the "git executable" field. 
      If {{% RSTUDIO %}} can't find it, you can help it by browsing to 
      the git program.
  * If you have installed {{< LATEX_LOGO >}} on your computer, 
    click on the SWeave tab, and select "knitr" for weaving
    `.Rnw` files, and choose `pdfLaTeX` for typesetting 
    {{< LATEX_LOGO >}} files into PDF.
    
## R Packages: {#installing-r-packages}

After you have R and {{% RSTUDIO %}} installed, you will need to install
a number of software packages that extend R for Bayesian data analysis.

* Cmdstanr

  The trickiest package to install is `cmdstanr`. I recommend that you 
  follow the 
  [detailed installation instructions](https://mc-stan.org/cmdstanr/articles/cmdstanr.html)
  on the `cmdstanr` web site.

  After you install `cmdstanr`, you will need to use it to install the 
  `cmdstan` software. For this, you will need to install a {{% CPP %}} 
  compiler and related tools before you can install `cmdstan`.

  (Don't worry, you won't need to do any programming in {{% CPP %}}.
  Stan writes the {{% CPP %}} code for you, based on your description of
  the statistical problem.)

  Follow the instructions at the `cmdstan` web page, 
  <https://mc-stan.org/docs/cmdstan-guide/installation.html>.
  There are instructions for installing the {{% CPP %}} toolchain for 
  Windows, MacOS, and Linux. 
  If you are using Windows, the simplest thing to do is install the 
  `Rtools4.5` software from the same place you installed R, or from 
  <https://cran.rstudio.org/bin/windows/Rtools/rtools45/rtools.html>

  After you've done this, you can go to the
  [main `cmdstanr` installation instructions](https://mc-stan.org/cmdstanr/articles/cmdstanr.html)
  and continue from there.

  The basic steps are to do the following at the R console in RStudio:


  #. First, check whether the {{% CPP %}} toolchain is set up correctly:

     ```
     library(cmdstanr)

     check_cmdstan_toolchain()
     ```

  #. If you get an error message, then run

     ```
     check_cmdstan_toolchain(fix = TRUE)
     ```

     to fix the toolchain configuration

  #. Next, install `cmdstan`

     ```
     options(mc.cores = parallel::detectCores() / 2 - 1)
     install_cmdstan()
     ```

     The line beginning `options(...` is optional. It tells R to use 
     multiple processor cores to install `cmdstan`, which can speed up 
     the installation considerably if you have a powerful processor in 
     your computer.

     If you run into difficulty, let me know and I will help you.

  If you are having trouble installing `cmdstan`, don't worry. We won't 
  use `cmdstan` until late in the semester, so go ahead and install the 
  other things, and there will be plenty of time for me to help you get 
  `cmdstan` installed and working on your computer.
  
* Other R packages

  This will be a lot easier. Open RStudio, go to the "Console" window in
  RStudio, and type
  ```
  install.packages(c("devtools", "pacman"))
  library(pacman)
  for (p in c("tidyverse", "ape", "bayesplot", "brms", 
    "broom", "coda", "dagitty", "flextable", 
    "ggdag", "ggformula", "ggmcmc", "ggrepel",  
    "ggthemes", "knitr", "loo", "mvtnorm", 
    "patchwork", "posterior", "psych", 
    "rcartocolor", "Rcpp", "rmarkdown", 
    "rprojroot", "sf", "shiny", "shinystan",
    "statebins", "tidybayes", "viridis", 
    "viridisLite", "wesanderson")) {
      p_install(p, character.only = TRUE, force = FALSE)
    }
  remotes::install_github("rmcelreath/rethinking")
  remotes::install_github("mjskay/tidybayes.rethinking")
  ```
  Now you should be good to go.

## Optional Tools: {#optional-tools}
  
### Installing the tinytex package {#installing-latex}

**It is optional to install the `tinytex` package.** 
You will be able to do all the work for the labs without it, but if you 
do install it, it will give you the option to produce nicely formatted 
PDF output from your RMarkdown files (for lab reports, presentations, 
etc.).

The R `tinytex` package installs a sophisticated typesetting system 
called {{< LATEX >}} on your computer. RMarkdown uses this system to 
generate PDF output.

The `tinytex` package needs to download a lot of files from the internet, 
and it can take 10 minutes or more to do so, even on a fast connection.
So it's a good idea to wait until you can let your computer run for a 
while, and until you're connected to a good fast internet connection, 
preferably one that doesn't charge you for data.

To install `tinytex`, go to the {{% RSTUDIO %}} console, and
you type the following:
  
```
install.packages('tinytex')
tinytex::install_tinytex()
```

If you want to uninstall `tinytex` later, you can just type this
command at the {{% RSTUDIO %}} console:

```
tinytex::uninstall_tinytex()`
```

### Installing {{<GIT_LOGO>}} {#installing-git}

Git is software for managing revisions as you develop software. You 
will not need it for this course, but it may be useful if you plan to 
develop complicated scripts for data analysis in the future.

If you have a Mac or Linux you may already have git installed. Test it 
by opening up a terminal window and typing `which git`. If you get a 
response like `/usr/bin/git` then it's installed. If there is no 
response, then you need to install git.
  
* **Windows:**
  * Download and install git from 
    [https://git-scm.com](https://git-scm.com)
    * Choose the default options for the installer.
  * Optionally, you might want to also install Tortoise Git, which 
    integrates git into the Windows explorer, so you can execute git 
    commands from the context menu when you right-click on files or 
    directories in the explorer.
    You can download Tortoise Git from 
    [https://tortoisegit.org/](https://tortoisegit.org/)
* **MacOS:**
    * If git is not already installed on your computer, you can download 
      and install it from [https://git-scm.com](https://git-scm.com)
* **Linux:**
    * If git is not already installed, you can install it from your 
      distribution's package manager:
      * `sudo apt-get install git` for Debian or Ubuntu
      * `sudo yum install git` or `sudo dnf install git` for Fedora, 
        Red Hat, and related distributions.

#### Introducing Youself to {{< GIT_LOGO >}} {#configuring-git}
              
**_Whatever operating system you're using,_** after you install git you 
will need to introduce yourself to git (you only need to do this once).
It is important for git to knows your name and email address so it can 
keep track of who is editing files when you are working collaboratively 
and so it gives you credit for the files you have authored and edited.
  
1. Open a terminal prompt:
   * On Windows, open a "git bash" window (git will give you the option 
     to do this when it finishes installing) or you can do so from the 
     Windows Start menu, under "Git".
   * On MacOS or Linux, open a regular terminal window (on MacOS, you 
     can use Finder to find the terminal application in the 
     "applications" folder).
2. Type the following at the terminal prompt:

   ```
   git config --global user.name "Your Name"
   git config --global user.email your.name@vanderbilt.edu
   ```
     
   using your real name and email.
       
You only need to introduce yourself to git one time after you install 
it. Then it will remember who you are every time you use it.

#### Getting an account on GitHUB {{< GITHUB_LOGO >}} {#github-account}

If you will be using Git, you may want to create a free account on the
GitHub website. This will allow you to use GitHub to store your work in 
the cloud, so you can get access it from other computers and have a
backup in case your computer dies.

* Go to [https://github.com](https://github.com "GitHub") and register
  for a free account
* After you have set up your account, go to 
  [GitHub Education](https://education.github.com/students "GitHub Student Accounts") 
  and register your account for the free extras you can get as a student.

## Resources for Learning More {#resources}

### {{< R_LOGO >}} and {{< RSTUDIO_LOGO >}} Resources {#r-resources}

* Our principal resource will be the book, 
  _[R for Data Science](https://r4ds.had.co.nz/ "Read R for Data Science online")_. 
  You can buy a printed copy or use the 
  [free online edition](https://r4ds.had.co.nz/ "Read R for Data Science online"),
  which is identical to the latest printed edition.

### {{< GIT_LOGO >}} and GitHUB {{< GITHUB_LOGO >}} Resources {#git-resources}

* There is a lot of free documentation about git at the 
  [git-scm](https://git-scm.com "Download git for your computer") 
  website, including a full 
  [Git reference manual](https://git-scm.com/docs "Read about git") and
  a free online book, 
  _[Pro Git](https://git-scm.com/book "Read the Pro Git book online")_
* Professor Jenny Bryan at the University of British
  Columbia, has written a lot of helpful tutorial material specifically 
  about using git and {{% GITHUB %}} with R and {{% RSTUDIO %}} at 
  [Happy Git and {{% GITHUB %}} for the useR](http://happygitwithr.com/ "Learn about using Git and GitHub with R and RStudio").
tutorial on using Git and GitHub with R and RStudio")
  at the 
  [{{% RSTUDIO %}} Webinars and Videos page](https://resources.rstudio.com/webinars "Watch more webinars and presentations about using R and RStudio"). 
  This tutorial walks you through all the steps of setting up git with 
  {{% RSTUDIO %}} and how to use it to keep track of your edits and 
  revisions, and synchronize your work with {{% GITHUB %}} (this serves 
  three functions: backing up your data to the cloud, sharing your data 
  with other people, and collaborating on writing code or documents with 
  other people).
