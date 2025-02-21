# Three-Body Potentials for LAMMPS

This repository contains implementations of three-body potentials for LAMMPS (Large-scale Atomic/Molecular Massively Parallel Simulator). The package includes two main potentials:

1. LJ3B (Lennard-Jones Three-Body)
2. FS3B (Fennel-Scheeres Three-Body)

## Overview

These potentials extend the traditional pair potentials by incorporating three-body interactions, which are crucial for modeling systems where angular dependencies and bond angles play important roles. The implementation is designed to work seamlessly with LAMMPS' existing framework.

### Features

- Full integration with LAMMPS
- Support for both two-body and three-body interactions
- Energy and force calculations
- Compatible with LAMMPS' parallel computing capabilities

## Installation

To use these potentials in LAMMPS, follow these steps:

1. Copy the following files to your LAMMPS source directory (`src/MANYBODY/`):
   ```
   pair_lj3b.cpp
   pair_lj3b.h
   pair_fs3b.cpp
   pair_fs3b.h
   ```

2. Recompile LAMMPS:
   ```bash
   cd /path/to/lammps/src
   make yes-manybody    # Enable the MANYBODY package if not already enabled
   make serial         # or make mpi for parallel version
   ```

## Usage

To use the potentials in your LAMMPS input script:

```lammps
# For LJ3B potential
pair_style lj3b
pair_coeff * * potential.lj3b element1 element2 ...

# For FS3B potential
pair_style fs3b
pair_coeff * * potential.fs3b element1 element2 ...
```

The potential files (`.lj3b` or `.fs3b`) should contain the necessary parameters for the interactions between different atom types.

## Example

An example directory (`lj3b-example/`) is provided with sample input files and potential parameters to help you get started.

## Citation

If you use these potentials in your research, please cite the appropriate references (see the manual for detailed citation information).

## License

This software is distributed under the GNU General Public License, consistent with LAMMPS' licensing terms.

## Contributing

Contributions are welcome! Please feel free to submit issues and pull requests.

## Contact

For questions and support, please open an issue in this repository.

