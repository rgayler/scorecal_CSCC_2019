FROM rocker/binder:3.6.0
LABEL maintainer='Ross W Gayler'
USER root
COPY . ${HOME}
RUN chown -R ${NB_USER} ${HOME}
USER ${NB_USER}
RUN wget https://github.com/rgayler/scorecal_CSCC_2019/raw/master/DESCRIPTION && R -e "options(repos = list(CRAN = 'http://mran.revolutionanalytics.com/snapshot/2019-09-09/')); devtools::install_deps()"
