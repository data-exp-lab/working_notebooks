# Description of notebooks in directory:

- v0.3.0-small.ipynb contains a slice and projection of one of yt's sample
  datasets, IsolatedGalaxy and uses some of display features we have
  implemented for yt slice and projection plots
- v0.3.0-xlarge.ipynb is a notebook demonstrating the widget features with a
  slice and projection dataset from Britton Smith's Pop II Prime dataset. The
  slice and projection datasets were generated with yt. 
- v0.3.0-large-slice.ipynb is a jupyter notebook with the slice Pop II
  prime dataset with temperature and density figures
- v0.3.0-large-projection.ipynb is a jupyter notebook with the projection
  Pop II prime dataset with temperature and density figures

[Paper](https://arxiv.org/abs/1504.07639) and
[Data](https://girder.hub.yt/#collection/5730acb5dd9119000142c361) for Pop II prime 


## Release Announcement

Hi all,

We're proud to announce the first release of the yt-widgets package, widgyts, which is a growing collection of Jupyter widgets for use in yt.

This package was designed so that you can interactively explore your data with the goal of making data exploration more accessible to yt users. You can pan, zoom, and update view parameters (like the colormap or the colormap bounds) quickly and learn where interesting features of your data are. We've uploaded two demonstration notebooks to give you a feel of the widget, one with IsolatedGalaxy and the other with slices of Britton's Pop II Prime dataset (thanks for making this dataset available Britton!). They can be found [here](https://girder.hub.yt/#raft/5c1ab9f5323d12000134e095). Alternatively, you can watch or look at the slides from Madicken's talk at SciPy 2018 about the initial stages of this project.

At present, the widget consists of a few compnents. The foundational widget is that of a variable-mesh image viewer, using Rust compiled to WebAssembly. The WebAssembly code is used to do the most performant-limiting calculations in the widget, resulting in much higher framerates than pure javascript rendering. Because WebAssembly was designed to interface with javascript, widget features can be built out using standard Python/javascript aspects of Jupyter widgets. You can read a little bit more about WebAssembly here and here if you'd like to learn more about it. Widgyts also currently has a widget that quickly converts data arrays to rgba colormapped arrays, and a tool to set up a standard set of widget controls.

This should work in all major browsers in the Jupyter notebook; at present Jupyterlab does not have support for easy distribution of wasm binaries. When able, we will build out support for this widget with Jupyterlab.

We'd like to thank the hard work done on other projects to make the development of widgyts possible. In particular, we'd like to thank the Jupyter team and the developers of ipywidgets. We'd also like to thank the rust core team and the wasm-pack developers for their awesome platforms.

Thanks for reading! If you'd like to give us any feedback on the widget, please don't hesitate to reach out.

Matthew Turk, Madicken Munk, and Nathanael Claussen
