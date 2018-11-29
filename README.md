[![CRAN_Status_Badge](http://www.r-pkg.org/badges/version/ETAS)](https://CRAN.R-project.org/package=ETAS)
[![CRAN_Download_Count](http://cranlogs.r-pkg.org/badges/ETAS)](https://CRAN.R-project.org/package=ETAS)
[![Build Status](https://travis-ci.org/jalilian/ETAS.svg?branch=master)](https://travis-ci.org/jalilian/ETAS)

# ETAS

This repository contains a copy of the R package 'ETAS'.

An earthquake catalog is a chronologically ordered list of time, coordinates of epicenter, magnitude and focal depth of all recorded earthquakes with magnitudes greater than or equal to a certain threshold that occurred inside or in the vicinity of a geographical region during a specified time period. Among different proposed models, the epidemic type aftershock sequence (ETAS) model is the most widely used statistical model to describe the underlying process that generates an earthquake catalogs. 

The space-time version of the ETAS model is a spatio-temporal marked point process model. It is a semi-parametric model that describes the background and triggering seismic activities in a geographical region and can be used for earthquake declustering. However, estimation of the ETAS model parameters is computationally challenging. The 'ETAS' package fits the ETAS model to an earthquake catalog.

## Installation

To install the package from [CRAN](https://CRAN.R-project.org/package=ETAS), run the following in R:
```R
install.packages('ETAS')
```

You can also intall the current version of the package on GitHub by running:
```R
require(remotes)
install_github('jalilian/ETAS')
```

If [remotes](https://github.com/mangothecat/remotes) is not installed, you should first run:

```R
install.packages('remotes')
```
 
Alternatively, the package can be installed by

```R
require(githubinstall)
githubinstall('ETAS')
```

If 'githubinstall' is not installed, first run:
```R
install.packages('githubinstall')
```

## Parallel computing

As of version 0.3, a new C++ code is implemented using the [Rcpp](http://www.rcpp.org/) package which allows multi-thread parallel computing on multi-core processors with OpenMP and [suported platforms](https://cran.r-project.org/doc/manuals/r-release/R-exts.html#OpenMP-support). The argument `nthreads` in `etas` function determines the number of threads to be used in the parallel region of the code. The detectCores function in [parallel](http://stat.ethz.ch/R-manual/R-devel/library/parallel/html/parallel-package.html) package can be consulted to find out the overall number of available threads on a given machine:
```R
parallel::detectCores()
```
Parallel computing (`nthreads > 1`) reduces the computation time for large earthquake catalogs. However, resource usage and limitations should be considered when setting `nthreads`.
