# molecular_conformations_ML

## Active learning algorithm for molecular conformations

This repository is a collection of Jupyter notebooks exploring active learning for molecular conformers. Active learning can be used to guide experiments or computations minimizing the need to perform expensive calculations. The example presented is predicting the energy of short chain polyethylene (3 monomers) conformations using Gaussian process regression (GPR).

The dataset is generated in [generate_medium_dataset](https://github.com/wood-b/molecular_conformations_ML/blob/master/notebooks/generate_medium_dataset.ipynb) notebook. Different conformations are defined by a set of torsion angles. Each oligomer has 3 unique torsion angles and each torsion angle can be rotated 360 degrees. Datasets are drawn from all possible torsional combinations. The energy of each conformer is calculated using the UFF potential implemented in RDKit.

An active learning algorithm is implemented in the [conformer_active_gpr](https://github.com/wood-b/molecular_conformations_ML/blob/master/notebooks/conformer_active_gpr.ipynb) notebook. The active learning loop selects the next conformers using the largest uncertainty from the GPR model.

The code currently implemented (7/16/19) is only a proof of concept. The representation/featurization (coulomb matrix eigenvalues), data splitting, and model (GPR) have not been optimized. This work is intended as a starting point/test bed for future work.

##Dependencies

- Python
- RDKit
- DeepChem
- scikit-learn
- Pandas
- NumPy
- Jupyter