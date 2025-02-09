FROM bioconductor/bioconductor_docker:latest
# Required libraries
RUN apt update && apt install -y \
    libglpk-dev 

# Using bioconductor dockers, as standard install too time consuming
# bioconductor based on rocker/rstudio, so missing some of the tidyverse
# packages I like. Took the below from the rocker instal_tidyverse.sh
ADD install_tidyverse.sh /tmp/
RUN bash /tmp/install_tidyverse.sh

# Bioconductor installs
RUN R -e 'BiocManager::install(ask = FALSE)' && \
    R -e 'BiocManager::install(c(\
    "microbiome" \
    ), ask = FALSE)'

# Install anything possible from CRAN
RUN install2.r --error \
    targets \
    vegan \
    httpgd \
    quarto \
    tarchetypes

# Install some packages from custom repos, often need for VSCode extentions
RUN install2.r --error --repos https://p3m.dev/cran/__linux__/noble/latest \
    languageserver && \
    install2.r --error --repos https://manuelhentschel.r-universe.dev \
    vscDebugger