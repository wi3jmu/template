# Jupyter notebook template

## Requirements

Installation instructions using conda (see https://docs.anaconda.com/anaconda/install/)
- Jupyter Notebook ```conda install -c anaconda jupyter```
- [jupyter-contrib-nbextensions](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/install.html)
```conda install -c conda-forge jupyter_contrib_nbextensions``` 
- [RISE](https://github.com/damianavila/RISE/) plugin ```conda install -c conda-forge rise ```

Installation via NPM (see https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
- Decktape (for pdf export) ```npm install -g decktape```

## Customization

Adapted from the [RISE documentation](https://rise.readthedocs.io/en/stable/index.html).

You can define *overlay* to build a constant background. It is wrapped in a `<div>` so it can be text or html. In this case, the user is entirely responsible for styling.

RISE looks for two css files to apply CSS changes on top of the slideshow view:

- rise.css will be applied to all notebooks in the current directory (see example)
- the_notebook_name.css will be applied to the_notebook_name.ipynb.

Both files need to be placed alongside with the notebook of interest, i.e. in the same directory. 

__a. Globally using RISE in [jupyter-contrib-nbextensions](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/install.html)__
1. Start the jupyter-notebook server
```jupyter notebook```
2. Open jupyter-contrib-nbextensions, e.g.:
```http://localhost:8888/nbextensions/``` 
3. Select the *RISE* plugin and add `<div>` container to *overlay*
```
<div class='background'><div class='logo'><img src='images/uniwue4c.png'></div><div class='bar'></div><div class='header'>Veranstaltung</br>Semester</br>Lehrstuhl für XYZ<br>Prof. Dr. XX</div>"
```

The CSS file defines the style of the different classes.

__b. In each notebook using the notebook metadata__
1. Start the jupyter-notebook server
```jupyter notebook```
2. Edit notebook meta data
```
{
 ...
 "rise": {
     "overlay": "<div class='background'><div class='logo'><img src='images/uniwue4c.png'></div><div class='bar'></div><div class='header'>Veranstaltung</br>Semester</br>Lehrstuhl für XYZ<br>Prof. Dr. XX</div>"
 }
}
```

## Export as pdf

1. Start the jupyter-notebook server (you don’t have to start the RISE presentation, you don’t even have to open any notebook at all):
```jupyter notebook```

2. Run decktape with:
```decktape rise <Jupyter-Notebook-URL><?token=xxx><Output-File>```

More concretely, it looks something like the following:
```
decktape rise -s 2000x1200 http://localhost:8888/notebooks/Vorlage.ipynb?token=1cb4ccc638b75a62a81821a919da954c06f9623797e9e292 Vorlage.pdf
```
Here, s defines the size of the slides deck viewport: <width>x<height> (e.g. '1280x720'). See the [decktape docs](https://github.com/astefanutti/decktape#90).

For more information, read the [RISE docs](https://rise.readthedocs.io/en/maint-5.5/exportpdf.html#using-decktape)



