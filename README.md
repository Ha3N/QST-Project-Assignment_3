Here is a professional summary of your current work, structured for a report or `README.md`.

### **Project Summary: Quantum State Tomography via Classical Shadows**

#### **1. Method**

This project implements **Quantum State Tomography (QST)** using the **Classical Shadows** protocol to efficiently reconstruct quantum states. The pipeline generates random -qubit quantum states and performs randomized Pauli measurements (measurements in , , and  bases) to construct "shadows" of the underlying state. The density matrix  is reconstructed using the linear inversion of the quantum channel. We utilize **fidelity** as the primary metric to validate the accuracy of the reconstructed state against the ground truth. The implementation includes a robust serialization pipeline using `pickle` to save intermediate model checkpoints (`models/model_<track>_<nqubits>.pkl`) ensuring reproducibility and data persistence across experimental runs.

#### **2. Limitations**

* **Statistical Noise (Shot Noise):** The accuracy of the reconstruction is fundamentally limited by the finite number of measurement shots. Lower shot counts result in higher variance in the estimated density matrix.
* **Classical Post-Processing Bottleneck:** While the measurement overhead is reduced compared to standard tomography, the classical memory required to store and process the reconstructed density matrix still scales exponentially () with the number of qubits.
* **Idealized Simulation:** The current validation assumes noise-free quantum gates and perfect readout. It does not currently account for hardware imperfections like decoherence, gate errors, or State Preparation and Measurement (SPAM) errors.

#### **3. Future Experiments**

* **Noise Robustness Analysis:** Introduce quantum noise models (e.g., depolarizing noise, thermal relaxation) to the simulator to evaluate the resilience of the Classical Shadows estimator under realistic hardware conditions.
* **Scalability Benchmarking:** Extend the experiments to higher qubit counts () to empirically map the scaling relationship between system size, required sample complexity (number of shadows), and reconstruction fidelity.
* **Observables vs. Full State:** Shift focus from full density matrix reconstruction to predicting properties (expectation values of specific observables) to fully leverage the logarithmic scaling advantage of Classical Shadows.
* **Machine Learning Integration:** Compare the classical shadow reconstruction fidelity against a Neural Network-based tomography approach (NN-QST) to assess potential improvements in sample efficiency.