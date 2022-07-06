# Tikz Plot Reproduction Experiment

Here, I try to replicate Figure 4 (just visual effects) from the ACL 2022 paper [Automatic Error Analysis for Document-level Information Extraction](http://dx.doi.org/10.18653/v1/2022.acl-long.274). 

The key challenges are:
- Use a custom font with the pdfLaTeX compiler. The mainstream solution is to use XeLaTeX, but this is said to be slower.
- Try some pgfplots and tikz commands. Though a python library [tikzplotlib](https://pypi.org/project/tikzplotlib/) provides some functionality, the result is not ideal. Heavy post editing is required to achieve the desired effect. Nevertheless, the template from tikzplotlib is quite useful.

Current limits are:
- The font in Figure 4 is Calibri, and the font in Figure 3 is Gill Sans MT. I managed to make the latter font work, but with the same pipeline, Calibri produces garbled characters for unknown reasons.

For the font pipeline, run `ttf2tfm custom.ttf -q -T T1-WGL4.enc -v custom.vpl custom.tfm >> custom.map` as instructed by this [tutorial](http://www.radamir.com/tex/ttf-tex.htm). Though four files are generated with a single .ttf file as the input, only the .ttf and .tfm files are needed. The .td file is copied from [here](https://www.overleaf.com/latex/examples/example-custom-font/htswqdkhqxjk) without further modification to its content. I tried modification but failed.
