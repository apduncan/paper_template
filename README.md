# Paper & Analysis Template
This is intended as a template for combining an analysis pipeline with
manuscript production in a reproducible(ish) way. 
Mainly intended to make it simpler for me to set up new projects, but I'm
trying to keep it general and potentially usable by others.
[targets](https://books.ropensci.org/targets/) is used to manage the
analysis & documentation build pipeline.
[This course](https://carpentries-incubator.github.io/targets-workshop/index.html) 
on targets is described as pre-alpha but is pretty good.
Manuscript writing and rendering is via a [quarto](https://quarto.org/) project.

Editing is intended to be through vscode connected to a 
[devcontainer](https://code.visualstudio.com/docs/devcontainers/containers#_getting-started)
which has a set of R based extensions installed.
The default container is based on 
[bioconductor/rstudio](https://www.bioconductor.org/help/docker/)
and so does have RStudio installed if you want to edit that way, but I have
not looked into how to mount the source directory to the container.
The R packages in the container by default are microbial ecology & metagenomics 
focused, but you can change the Dockerfile on your fork.
Default Bioconductor packages & microbiome are installed, which can be very
time consuming when building!

## Running docker containers on Mac/Windows
The docker engine and cli are free, but docker desktop requires a license.
For Mac, you can run containers using
[colima](https://github.com/abiosoft/colima) instead.
For Windows, you can run docker within WSL2.


## targets functions
Anything in `R/std` I've intended to be quite general functions. For specfic
types of analyses I do frequently, I've made some subdirectories to organise
scripts a bit more.

## Private forks
You can't make a private fork of a public repo.
However, likely you want to write you analysis and paper in private.
To make a copy which can still pull from upstream, follow 
[this gist](https://gist.github.com/0xjac/85097472043b697ab57ba1b1c7530274)
ignore step 7 onwards.

## vscode
Default exensions:
* R language support
* R debugger
* docker

Set up to use 
[httpgd](https://github.com/REditorSupport/vscode-R/wiki/Plot-viewer)
for plot display by default