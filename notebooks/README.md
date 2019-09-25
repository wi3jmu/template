# wi3jmu Jupyter notebook template

## Requirements

Installation using conda (see https://docs.anaconda.com/anaconda/install/)
- Jupyter Notebook 
```conda install -c anaconda jupyter```
- [jupyter-contrib-nbextensions](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/install.html): 
conda install -c conda-forge jupyter_contrib_nbextensions
) 
- [RISE](https://github.com/damianavila/RISE/) plugin.
conda install -c conda-forge rise 
- Decktape (for pdf export)
npm install -g decktape

## Customization

### Globally using [jupyter-contrib-nbextensions](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/install.html)

### Per notebook using the notebook metadata

## Export as pdf

1. Start the jupyter-notebook server (you don’t have to start the RISE presentation, you don’t even have to open any notebook at all):

jupyter notebook

NOTE: Make sure autoLaunch option is disabled, otherwise the decktape plugin will exit from the slideshow view before printing the slides. Discussion about this behavior lives at https://github.com/astefanutti/decktape/issues/110.

2. Run decktape with:

$(npm bin)/decktape rise <Jupyter-Notebook-URL> <Output-File>

More concretely, it looks something like the following:
e.g.

decktape rise -s 2000x1200 http://localhost:8888/notebooks/Vorlage.ipynb?token=1cb4ccc638b75a62a81821a919da954c06f9623797e9e292  Vorlage.pdf

For more information, read the (RISE docs)[https://rise.readthedocs.io/en/maint-5.5/exportpdf.html#using-decktape]



