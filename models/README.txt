Tomography Checkpoints
======================
This directory contains serialized QuantumModel objects.

Naming Convention:
model_<track>_<nqubits>.pkl

How to Load:
Use the static method `QuantumModel.load(path)` defined in the notebook.

Example:
model = QuantumModel.load('models/model_density_matrix_3.pkl')