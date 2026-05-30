# Hartree-Fock/STO-3G in Python

Educational Python implementation of a minimal-basis restricted Hartree-Fock self-consistent-field calculation for a closed-shell, two-electron diatomic molecule.

The project is based on the pedagogical FORTRAN program associated with Appendix B of Szabo and Ostlund's *Modern Quantum Chemistry: Introduction to Advanced Electronic Structure Theory*. The aim is not to create a production quantum-chemistry package, but to demonstrate scientific programming, numerical methods, matrix-based Hartree-Fock theory, and the translation of legacy scientific code into modern Python.

## What the program does

The default calculation performs a minimal-basis Hartree-Fock calculation for HeH+ using an STO-3G basis. The program evaluates one-electron and two-electron integrals, builds the overlap matrix, core Hamiltonian, Fock matrix, and density matrix, and iterates the self-consistent-field procedure until convergence.

Although the repository name refers to STO-3G, the implementation follows the STO-nG structure of the original pedagogical program and supports n = 1, 2, or 3.

## Technical features

* Restricted Hartree-Fock calculation for a two-electron diatomic molecule
* STO-nG support for n = 1, 2, or 3
* Default HeH+ calculation in an STO-3G minimal basis
* One-electron and two-electron integral evaluation
* Self-consistent-field iteration
* Density-matrix convergence check
* NumPy-based matrix operations
* Object-oriented Python structure
* Type hints and dataclass result container
* Fortran-style numerical output formatting for comparison with the original program

## Installation

Clone the repository and install the required dependency:

```bash
pip install -r requirements.txt
```

## Usage

Run the default calculation:

```bash
python hartree_fock_sto3g.py
```

Use the calculation from another Python script:

```python
from hartree_fock_sto3g import hfcalc

result = hfcalc(iop=0)
print(result.total_energy)
print(result.iterations)
```

## Default calculation

The default parameters reproduce the classic HeH+ minimal-basis example:

* basis: STO-3G
* internuclear distance: R = 1.4632 bohr
* zeta1 = 2.0925
* zeta2 = 1.24
* ZA = 2.0
* ZB = 1.0

The calculation returns the final electronic energy, total energy, number of SCF iterations, density matrix, molecular-orbital coefficients, orbital energies, overlap matrix, core Hamiltonian, Fock matrix, two-electron contribution, and Mulliken PS matrix.

## Why this project is useful

This project demonstrates how a compact legacy scientific program can be translated into readable Python while preserving the original numerical algorithm. It is intended as a portfolio and learning project showing scientific programming, matrix-based numerical methods, code translation, and computational chemistry knowledge.

## Attribution

This project is an educational Python translation/reimplementation of the pedagogical two-electron SCF program from Appendix B of:

A. Szabo and N. S. Ostlund, *Modern Quantum Chemistry: Introduction to Advanced Electronic Structure Theory*.

The original FORTRAN source is available from the Computational Chemistry List software archive.

## License note

No open-source license is currently provided for this repository because the project is based on an educational translation/reimplementation of a published pedagogical FORTRAN program. The repository is intended as a portfolio and learning project with attribution to the original source.

## Maintainer

Károly Kubicskó
