# scorecal_CSCC_2019

<!-- badges: start -->
[![DOI](https://zenodo.org/badge/205238383.svg)](https://zenodo.org/badge/latestdoi/205238383)
[![Launch Rstudio Binder](http://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/rgayler/scorecal_CSCC_2019/master?urlpath=rstudio)
<!-- badges: end -->

## Run this notebook in the cloud

**To run this code without installing anything**,
click on the "launch binder" badge above.
This will launch Rstudio on a free, small, cloud instance.
It may take a minute or two to launch and initialise.

You will eventually get a web browser tab with the Rstudio IDE running in it,
and with this `scorecal_CSCC_2019` project open in it.
Open the file `scorecal_CSCC_2019.Rmd` for editing in the Rstudio IDE and click the `Knit` button just above the code.
This will execute all the code in the notebook and render the results to `scorecal_CSCC_2019.pdf`,
which will open in a pop-up window.

The notebook took about two minutes to knit when I tried it.
There will be many red messages in the `R Markdown` tab while the PDF file is being rendered.
These can be ignored (provided you get sensible looking output).
The only difference I could spot is that the font used in the archived presentation 
is missing from the cloud instance,
and the default font used in its place has a slightly larger spacing,
resulting in some text on the slides being slightly too long for the page. 

You can edit the code in the notebook and re-knit it to see what happens.
More likely, you will want to edit the code and just execute it in the notebook without knitting it to PDF.
The results of each code chunk will be displayed in the notebook immediately after the code chunk.
To do that, you will have to find out how to drive Rstudio.

The cloud instance is small, and has various constraints imposed on it.
The limitations at the time of writing this are:

* The server has limited memory so you cannot load large datasets or run big computations
* This is meant for interactive and ephemeral interactive coding so an instance will die after 10 minutes of inactivity.
* An instance cannot be kept alive for more than 12 hours

The [holepunch](https://github.com/karthik/holepunch) package was used to convert this repository to a docker image for cloud execution. 

## Generate the conference presentation

**This repository contains an executable `R` notebook**
that generates the presentation "scorecal - Empirical score calibration under the microscope"
given by 
[Ross W. Gayler](http://www.rossgayler.com)
on 2019-08-30
at the conference 
[Credit Scoring & Credit Control XVI](http://crc.business-school.ed.ac.uk/category/conference-papers/2019/)
in Edinburgh, UK.
The presentation, as given, is archived at [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3381658.svg)](https://doi.org/10.5281/zenodo.3381658)

The notebook contains all the `R` code
used to simulate and analyse the data
and generate the plots.
This is in the form of a script rather than a package.
You are free to modify the script to see what happens.
If you are using the Rstudio IDE,
edit the notebook file `scorecal_CSCC_2019.Rmd` and execute the relevant code chunks.
The results will be displayed in the notebook immediately after the code chunks.
Click the `Knit` button to render a new copy of the presentation slides with the results of your altered code.

This notebook requires the [`binb`](http://github.com/eddelbuettel/binb) package 
to enable rendering the output as a PDF presentation.
It uses the `metropolis` template to set the style of the presentation.
These require a variety of LaTeX tools and fonts to be installed,
in addition to the `rmarkdown` and `knitr` infrastructure.
See (http://github.com/eddelbuettel/binb) for `binb` installation advice.

**Conference abstract**

Score calibration is the process of empirically determining the relationship between a score
and an outcome on some population of interest, 
and scaling is the process of expressing that relationship in agreed units. 
Calibration is often treated as a simple matter and attacked with simple tools –
typically, either assuming the relationship between score and log-odds is linear 
and fitting a logistic regression with the score as the only covariate, 
or dividing the score range into bands 
and plotting the empirical log-odds as a function of score band. 

Both approaches ignore some information in the data. 
The assumption of a linear score to log-odds relationship is too restrictive 
and score banding ignores the continuity of the scores. 
While a linear score to log-odds relationship is often an adequate approximation, 
the reality can be much more interesting, 
with noticeable deviations from the linear trend. 
These deviations include large-scale non-linearity, 
small-scale non-monotonicity, 
discrete discontinuities, 
and complete breakdown of the linear trend at extreme scores. 

Detecting these effects requires a more sophisticated approach 
to empirically determining the score to outcome relationship. 
Taking a more sophisticated approach can be surprisingly tricky: 
the typically strong linear trend can obscure smaller deviations from linearity; 
detecting subtle trends requires exploiting the continuity of the scores, 
which can obscure discrete deviations; 
trends at extreme scores (out in the data-sparse tails of the distribution of scores) 
can be obscured by trends at less extreme scores (where there is more data); 
score distributions with some specific values that are relatively common 
can disrupt methods relying on continuity; 
and any modelling technique can introduce its own biases. 

Over the years I have developed a personal approach to these issues in score calibration 
and implemented them as an open source, publicly accessible R package for score calibration. 
I discuss these technical issues in empirical score calibration 
and show how they are addressed in the scorecal package.
