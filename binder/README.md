# How to setup *binder* for a classroom

Choose languages for your environment (delete unnecessary files config files) and add the required packages.

## Python
_environment.yml_ - Install a Python environment. It also allows to install R packages or include *pip* instructions, e.g., to install *Julia*.

## R

_install.R_ - Install an R/RStudio/Shiny environment
_runtime.txt_ - Specify R runtimes

### Julia

_Project.toml_ - Install a Julia environment. A Project.toml (or JuliaProject.toml) file can specify both the version of Julia to be used and a list of Julia packages to be installed. If a Manifest.toml is present, it will determine the exact versions of the Julia packages that are installed.


### Custom

_postBuild_ - Run code after installing the environment
The example postBuild installs and enables [jupyter_contrib_nbextensions](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/install.html) and the [RISE](https://github.com/damianavila/RISE/) plugin.

For more information, read the Binder documentation: https://mybinder.readthedocs.io/en/latest/