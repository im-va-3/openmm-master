[![GH Actions Status](https://github.com/openmm/openmm/workflows/CI/badge.svg)](https://github.com/openmm/openmm/actions?query=branch%3Amaster+workflow%3ACI)
[![Conda](https://img.shields.io/conda/v/conda-forge/openmm.svg)](https://anaconda.org/conda-forge/openmm)
[![Anaconda Cloud Badge](https://anaconda.org/conda-forge/openmm/badges/downloads.svg)](https://anaconda.org/conda-forge/openmm)

## OpenMM: A High Performance Molecular Dynamics Library

### Introduction

[OpenMM](https://openmm.org) is a toolkit for molecular simulation. It can be used either as a stand-alone application for running simulations, or as a library you call from your own code. It
provides a combination of extreme flexibility (through custom forces and integrators), openness, and high performance (especially on recent GPUs) that make it truly unique among simulation codes.  

### Getting Help

Need help using OpenMM?  There are several places that you can find it:
- [Documentation](https://docs.openmm.org/):
  - [User Manual](https://docs.openmm.org/latest/userguide/)
  - [Python API Reference](https://docs.openmm.org/latest/api-python/)
  - [C++ API Reference](https://docs.openmm.org/latest/api-c++/)
- [Getting Support](SUPPORT.md):
  - [Frequently Asked Questions](https://github.com/openmm/openmm/wiki/Frequently-Asked-Questions)
  - [Discussion Forum](https://github.com/openmm/openmm/discussions)
  - [Issue Tracker](https://github.com/openmm/openmm/issues)
- [Learning Resources](https://openmm.github.io/openmm-cookbook/latest):
  - [OpenMM Tutorials](https://openmm.github.io/openmm-cookbook/latest/tutorials)
  - [OpenMM Cookbook](https://openmm.github.io/openmm-cookbook/latest/cookbook)
  - [OpenMM Examples](examples/README.md)
- [Contributing to OpenMM](CONTRIBUTING.md):
  - [Developer Guide](https://docs.openmm.org/latest/developerguide/)

### License Information

OpenMM is free and open-source software.  There are several licenses which cover
different parts of OpenMM, but most of the source code is covered by the MIT
license or the GNU Lesser General Public License (LGPL).  Portions copyright
© 2008-2025 Stanford University and the Authors.  For more details, see
[Licenses.txt](docs-source/licenses/Licenses.txt).


## Step-by-step user guide

1. **Install OpenMM.** In a fresh Python environment, use <code>python -m pip install openmm</code> or the conda-forge package. Check the installation with <code>python -m openmm.testInstallation</code> and read the platform notes if you expect GPU execution.
2. **Choose an input system.** Start with a PDB file and a compatible force field. Place a file named <code>input.pdb</code> in the current directory, then run <code>python examples/python-examples/simulatePdb.py</code>. The script minimizes the structure, runs 10,000 steps, and writes a DCD trajectory; the [examples guide](examples/README.md) also covers Amber, CHARMM, and GROMACS inputs.
3. **Build the molecular system.** Load the topology/coordinates, choose force-field XML files, create the System, select constraints and nonbonded treatment, and confirm the system can be serialized.
4. **Choose dynamics and hardware.** Create an integrator with temperature, friction, and time step as appropriate; create a Simulation; select a CPU/CUDA/OpenCL/Reference platform and any platform properties.
5. **Run and save.** Set positions and velocities, minimize if needed, add reporters for state/energy/trajectory, then advance the requested number of steps. Save checkpoints and final structures for restart and analysis.
6. **Customize physics.** Add custom forces or integrators, parameterize the system, and compare against a built-in force field before optimizing or extending the model.

### Functionality map

- Standalone molecular-dynamics application APIs and Python/C++ library interfaces.
- Force-field construction, custom forces, integrators, constraints, barostats, virtual sites, parameter updates, and platform selection.
- CPU/GPU execution, platform properties, checkpointing, reporters, trajectories, system serialization, Python/C++ APIs, C/Fortran bindings, and benchmark/utility scripts.
- Follow the [User Guide](https://docs.openmm.org/latest/userguide/), [Python API](https://docs.openmm.org/latest/api-python/), [C++ API](https://docs.openmm.org/latest/api-c++/), and local [examples](examples/) for every force, integrator, and platform option.

