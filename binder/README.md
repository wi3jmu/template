# How to set up *Binder*

- Choose a language for your environment
- Add the required packages
- Delete unnecessary config files

## Python and R
__environment.yml__ - Install a Python environment. It also allows to install R packages or include *pip* instructions


## Julia

__Project.toml__ - Install a Julia environment. A Project.toml (or JuliaProject.toml) file can specify both the version of Julia to be used and a list of Julia packages to be installed. If a Manifest.toml is present, it will determine the exact versions of the Julia packages that are installed.


## Custom

__postBuild__ - Run code after installing the environment
The example postBuild installs and enables the [Split Cell](https://github.com/ipython-contrib/jupyter_contrib_nbextensions/tree/master/src/jupyter_contrib_nbextensions/nbextensions/splitcell) and the [RISE](https://github.com/damianavila/RISE/) plugin.

For more information, read the Binder documentation: https://mybinder.readthedocs.io/en/latest/

## RStudio and Shiny (not included here)

__install.R__ - Install an R/RStudio/Shiny environment

__runtime.txt__ - Specify R runtimes

See [Binder sample repos](https://mybinder.readthedocs.io/en/latest/sample_repos.html).
