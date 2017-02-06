R interface to Python
================

Installation
------------

You can install the rpy package from GitHub as follows:

``` r
devtools::install_github("rstudio/rpy")
```

Note that the rpy package includes native C/C++ code so it's installation requires [R Tools](https://cran.r-project.org/bin/windows/Rtools/) on Windows and [Command Line Tools](http://osxdaily.com/2014/02/12/install-command-line-tools-mac-os-x/) on OS X. If the package installation fails because of inability to compile then install the appropriate tools for your platform based on the links above and try again.

### Locating Python

When it is loaded the rpy R package scans the system for a compatible version of Python. If automatic detection doesn't work or if you want to exercise more control over which version of python is used you can specify an explicit `RPY_PYTHON` environment variable, for example:

``` r
Sys.setenv(RPY_PYTHON="/usr/local/bin/python")
library(rpy)
```

The rpy package will look in this location first, then look for python on the system `PATH`, then scan additional locations where python is conventionally installed (e.g. `/usr/local/bin`, `/opt/python/bin`, etc.).

### Verifying Installation

You can verify that your installation is working correctly by running this script:

``` r
library(rpy)
sys = import("sys")
sys$version
```
