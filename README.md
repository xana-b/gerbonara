[![pipeline status](https://gitlab.com/gerbolyze/gerbonara/badges/master/pipeline.svg)](https://gitlab.com/gerbolyze/gerbonara/commits/master)
[![coverage report](https://gitlab.com/gerbolyze/gerbonara/badges/master/coverage.svg)](https://gitlab.com/gerbolyze/gerbonara/commits/master)
[![pypi](https://img.shields.io/pypi/v/gerbonara)](https://pypi.org/project/gerbonara/)
[![aur](https://img.shields.io/aur/version/python-gerbonara)](https://aur.archlinux.org/packages/python-gerbonara/)

# bugfix clone

This repo is a clone of the gerbolyze gerbonara repo including a bugfix which prevented me from merging multilayer PCBs. 
Note that the bugfix was done without proper understanding of the codebase with the help of the claude AI.

The error was AttributeError: 'tuple' object has no attribute 'merge' when trying to merge multilayer pcbs created with KiCad 9.0.

The fix was in
 /home/alex/gerbonara/gerbonara/layers.py:1395:  Extract layer objects from tuples: [layer for _, layer in
  self.copper_layers[1:-1]]

I tested with the command gerbonara merge a a out
a/a and out being the directories in this repo. 

# Gerbonara

Tools to handle Gerber and Excellon files in Python.

This repository is a friendly fork of [phsilva's pcb-tools](https://github.com/curtacircuitos/pcb-tools) with
[extensions from opiopan](https://github.com/opiopan/pcb-tools-extension) integrated. We decided to fork pcb-tools since
we need it as a dependency for [gerbolyze](https://gitlab.com/gerbolyze/gerbolyze) and pcb-tools was sometimes very
behind on bug fixes.

# Installation

Arch Linux:

```
yay -S python-gerbonara
```

Python:

```
pipx install gerbonara
```

# Documentation and Examples

Documentation can be found at:

https://gerbolyze.gitlab.io/gerbonara

# Issues

Please file any bugs at our issue tracker:

https://gitlab.com/gerbolyze/gerbonara/-/issues

---

Made with ❤️ and 🐍.
