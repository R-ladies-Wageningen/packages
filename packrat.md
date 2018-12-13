# Introduction to the usage of Packrat

To get a first introduction about what you can do with packrat, you can follow this short tutorial. You can get more information about packrat [here](https://rstudio.github.io/packrat/)

On the server do the following:

```
mkdir ~/test/

R

install.packages("packrat")
packrat::init("~/test/")
install.packages("reshape2")
packrat::snapshot()
quit()

ls -l ~/test
# drwxr-xr-x 6 fleurg domain users 9 Nov  2 10:00 packrat

ls -l ~/test/packrat
# total 28
# -rw-r--r--  1 fleurg domain users 8408 Nov  2 10:00 init.R
# drwxr-xr-x  3 fleurg domain users    3 Nov  2 10:00 lib
# drwxr-xr-x  3 fleurg domain users    3 Nov  2 10:00 lib-R
# drwxr-xr-x  3 fleurg domain users    3 Nov  2 10:00 lib-ext
# -rw-r--r--  1 fleurg domain users  849 Nov  2 10:28 packrat.lock
# -rw-r--r--  1 fleurg domain users  368 Nov  2 10:00 packrat.opts
# drwxr-xr-x 10 fleurg domain users   10 Nov  2 10:28 src
```

On local laptop download ~/test/

```
cd test
R

#Packrat is not installed in the local library -- attempting to bootstrap an #installation...
#> Installing packrat into project private library:
#- 'packrat/lib/x86_64-apple-darwin15.6.0/3.5.1'
#* installing *source* package ‘packrat’ ...
#** package ‘packrat’ successfully unpacked and MD5 sums checked
#** R
#** inst
#** byte-compile and prepare package for lazy loading
#** help
#*** installing help indices
#** building package indices
#** testing if installed package can be loaded
#* DONE (packrat)
#> Attaching packrat
#> Restoring library
#> Packrat bootstrap successfully completed. Entering packrat mode...
#Packrat mode on. Using library in directory:
#- "~/Documents/Projects/packrat/packrat/lib"

packrat::status()


#The following packages are tracked by packrat, but are no longer available in the #local library nor present in your code:
#             _
#    Rcpp       0.12.19
#    glue       1.3.0
#    magrittr   1.5
#    plyr       1.8.4
#    reshape2   1.4.3
#    stringr    1.3.1

#You can call packrat::snapshot() to remove these packages from the lockfile, or if #you intend to use these packages, use packrat::restore() to restore them to your #private library.

packrat::restore()

#Installing Rcpp (0.12.19) ...
#	OK (downloaded binary)
#Installing glue (1.3.0) ...
#	OK (downloaded binary)
#Installing magrittr (1.5) ...
#	OK (downloaded binary)
#Installing stringi (1.2.4) ...
#	OK (downloaded binary)
#Installing plyr (1.8.4) ...
#	OK (downloaded binary)
#Installing stringr (1.3.1) ...
#	OK (downloaded binary)
#Installing reshape2 (1.4.3) ...
#	OK (downloaded binary)
#Warning message:
#In packrat::restore() :
#  The most recent snapshot was generated using R version 3.4.2

packrat::status()

#Up to date.
