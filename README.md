# Rings_and_Fields
repo for MATH 385 Rings and Fields
## Intro
For some code it may be necessary to add an additional latex package called maxiplot, which can be found [here](https://sourceforge.net/p/maxima/website/ci/master/tree/contrib/maxiplot/maxiplot.sty). Following that, create a directory (much like amsmath) and place the sty file there (I named mine maxiplot). Then run,

``` shell
sudo texhash
```
and the latex documents should now compile.

I also used the following script to automate some of the process

``` shell
#!/bin/bash
pdflatex $1.tex
maxima -b $1.mac
pdflatex $1.tex
```
