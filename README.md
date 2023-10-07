# pyhep-2023


[![Binder](https://binderhub.ssl-hep.org/badge_logo.svg)](https://binderhub.ssl-hep.org/v2/gh/APN-Pucky/pyhep-2023/HEAD)

This repository contains the material for the [PyHEP 2023](https://indico.cern.ch/event/1252095/timetable/#2-feynman-diagrams-in-python-r) workshop. The abstract is given below.


## Feynman diagrams in python: Revamping feynml and pyfeyn¶ 30m

feynml is a project to develop an XML dialect for describing Feynman diagrams as used in quantum field theory calculations. A primary goal is the creation of a clear and definitive XML representation of Feynman diagram structures, serving as a standard that can be effortlessly translated into diverse formats. Similarly to HTML/CSS the physical/topological content is separated from the stylized representation.

That graphical representation can be realized through pyfeyn2, which took the approach of pyfeyn and extended it to a broader range of render engines namely matplotlib, PyX, tikz, ASCII, Unicode, feynmp and the DOT language. The package allows for manual or automatic placement of vertices, enabling customization and flexibility from within a Notebook.

The main difference to existing Mathematica-based solutions lies in the modular approach. This modularity enables easy interfacing with a range of tools. For instance, LHE and HEPMC files can be visualized as Feynman diagrams through pyLHE and pyHEPMC. Additionally, theoretical computations are streamlined through interfaces such as the python-based UFO standard and qgraf. Further, the transformation of diagrams into amplitudes is supported, which can be further processed with tools like form or sympy.

The projects are hosted on github
https://github.com/APN-Pucky/pyfeyn2
https://github.com/APN-Pucky/feynml
