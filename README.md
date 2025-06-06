# Make Reading Lists from $\TeX$ files

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/julowe/binder-reading-lists/HEAD)

This repository contains a complete .tex file to make the GI Eastern Classics Reading list.
It will (soon?) contain some code to make a reading list from a .xlsx file

The jupyter notebook that opens up by default when you click the above badge contains usage information, but that plus some is included below. Live preview of the .tex file and any changes you make is supported, and you can then download the pdf file.

I chose $\TeX$ because it gives control over formatting options
but is still pretty human-readable
and (being plain text vs the byzantine word .doc format) changes are more easily tracked.

There is a lot of preamble in the .tex files for all the functionality of printing class headers with or without the class dates, and a few other features. 
(Why is it not in a .sty files? Because I easily see the .tex file being sent around and split up from the .sty file, creating just another hurdle towards usage. So this way is messy, but will ~always work as a standalone file.)
Change the '0' to a '1' on Line 15 of the .tex file to turn on class dates with Session number
(i.e. change `\setcounter{printSessionDate}{1}` to `\setcounter{printSessionDate}{0}` )

## Info on Jupyter Notebook server

The notebook defaults to using XeLaTex to render PDFs, this works better for unicode characters.

This repository was templated from a [non-working example](https://github.com/binder-examples/latex) by the people who run [mybinder.org](https://mybinder.org/) that [I updated](https://github.com/julowe/latex/tree/issue-14-fails-to-build) which demonstrates using latex alongside matplotlib.
This repository also makes use of [JupyterLab Latex](https://github.com/jupyterlab/jupyterlab-latex) to render tex files in Jupyter lab. This requires a few different build components:

- `apt.txt` for apt-installing the latex and xetex components
- `environment.yml` for installing the python dependencies
- `postBuild` for manually updating tex packages from [CTAN](https://ctan.org/) and then forcing matplotlib to build the font cache
