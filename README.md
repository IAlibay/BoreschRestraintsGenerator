MDRestraintsGenerator
==============================
[//]: # (Badges)
[![Travis Build Status](https://travis-ci.com/Bigginlab/MDRestraintsGenerator.svg?branch=master)](https://travis-ci.com/Bigginlab/MDRestraintsGenerator)
[![AppVeyor Build status](https://ci.appveyor.com/api/projects/status/REPLACE_WITH_APPVEYOR_LINK/branch/master?svg=true)](https://ci.appveyor.com/project/REPLACE_WITH_OWNER_ACCOUNT/MDRestraintsGenerator/branch/master)
[![codecov](https://codecov.io/gh/Bigginlab/MDRestraintsGenerator/branch/master/graph/badge.svg)](https://codecov.io/gh/Bigginlab/MDRestraintsGenerator/branch/master)

# MDRestraintsGenerator

A framework for generating restraints for MD simulations (from MD simulations).

The code currently only looks at BoreschRestraints, but we aim to extend to:

- Hardwall restraints
- Harmonic restraints
- Attach Pull Restraint style restraints
- Complex multidimensional restraints

Note: This is considered to be pre-production code, a lot is left to do and
major changes will happen at any time.

## Installation

Installation is currently only possible from source. This can be done in the following manner:

```
git clone https://github.com/bigginlab/MDRestraintsGenerator.git
cd MDRestraintsGenerator
pip install .
```

## How to use

The code currently only implements a means of deriving Boresch restraints for GROMACS simulations.
To achieve this, the following underlying methods are provided:

  1) A function to pick stable points in ligands for restraint attachment
     (`search.find_ligand_atoms`).
  2) A class for picking host restraint addition points (`search.FindHostAtoms`).
  3) A class for analysing a list of possible Boresch restraints over a given MD simulation and
     finding the most stable choice of restraint atoms (`restraints.FindBoreschRestraint`).

An example use script is provided under `scripts.BoreschRestraintGMX.py`. Documentation docstrings
are provided for all functions and classes. These can be accessed by calling `help(function)`.

## Testing

A set of unit tests are provided under `MDRestraintsGenerator.tests`. To run these you will need
to have `pytest` installed. The tests can be run in the following manner:
```
pytest -v MDRestraintsGenerator.tests
```

### Dependencies

- MDAnalysis
- NumPy
- SciPy
- Matplotlib

### Copyright

Copyright (c) 2020, Irfan Alibay


#### Acknowledgements
 
Project based on the 
[Computational Molecular Science Python Cookiecutter](https://github.com/molssi/cookiecutter-cms) version 1.3.
