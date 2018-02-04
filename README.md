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

## On Notes
Towards being as transparent as possible, I'm using OCR to convert screenshots of the e-text to text files, which I then review and modify for TeX output. Right now, I have the benefit of being able to use wolfram scripts to automate the process and create one large text file. I'm working on using open source OCR to accomplish this in the future. My script looks like this,

``` mathematica
#!/usr/bin/env wolframscript

images=Import["./Selection_*"];
text=Map[TextRecognize,images];
Export["./Selection.txt",text];
```

which I copy into the directory with the screenshots and run

``` shell
wolframscript <script_name>
```
