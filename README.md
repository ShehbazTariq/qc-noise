# Quantum Noise Analysis for Quantum Addition

This repository is part of the **Quantum Computing Mentorship Program Screening Task**. It involves analyzing the effects of noise on quantum addition using quantum circuits. The repository contains implementations of several tasks that demonstrate how noise impacts quantum computations, and provides methods for adding noise, optimizing circuits, and evaluating results.

## Tasks Overview

### Task 1: Noise Model Creation
- **Objective**: Develop a simple noise generator to simulate the effects of noise on a quantum circuit.
- **Details**: Used Pauli operators (X, Y, Z) to create a function that simulates noise after both one-qubit and two-qubit gates. The function takes the probability of applying noise as input and adds it to a quantum circuit.

### Task 2: Gate Basis Transformation
- **Objective**: Transform a general quantum circuit to use a specific gate basis: {CX, ID, RZ, SX, X}.
- **Details**: Created a function that transforms a quantum circuit to use the specified gate set, which is often required for executing the circuit on specific quantum hardware that supports only certain gates.

### Task 3: Quantum Addition using Draper Adder Algorithm
- **Objective**: Implement the Draper adder algorithm to add two numbers using a quantum circuit.
- **Details**: Built a quantum addition function (`quantum_sum`) using the Quantum Fourier Transform (QFT). The function takes two integers as input and performs the addition on a quantum circuit using the QFT and inverse QFT. Noise effects are analyzed by adding noise to this circuit.

### Task 4: Effects of Noise on Quantum Addition
- **Objective**: Analyze the impact of noise on the quantum addition performed in Task 3.
- **Details**: Added noise to the quantum addition circuit and evaluated how different noise levels affect the output. This task involved answering several key questions about noise effects:
  - **How does the noise affect the results?**
    - Noise reduces the accuracy of the results, causing deviations from the correct sum. Higher noise levels lead to more errors in the final state and reduced fidelity compared to the ideal, noiseless state.
  - **Is there a way to decrease the effect of noise?**
    - Methods such as quantum error correction, gate count reduction, noise-aware compilation, and pulse optimization can be used to reduce the impact of noise.
  - **How does the number of gates affect the results?**
    - The number of gates directly impacts the noise level, as each gate introduces potential errors. More gates mean a higher probability of accumulating errors, reducing the overall fidelity.

## Code Structure
- **`qft(n)`**: A function that implements the Quantum Fourier Transform on `n` qubits.
- **`quantum_sum(a, b)`**: Implements the Draper adder algorithm for quantum addition of two integers `a` and `b`.
- **`simulate_with_noise(a, b, p1, p2)`**: Simulates the `quantum_sum` function with added noise using the Pauli noise model, where `p1` and `p2` represent noise levels for one-qubit and two-qubit gates respectively.
- **`compute_fidelity(density_matrix_noiseless, density_matrix_noisy)`**: Computes the fidelity between the noiseless and noisy density matrices to evaluate how closely the noisy result matches the ideal outcome.

## Running the Code
1. Install the required dependencies from the `requirements.txt`.
2. Run the Jupyter Notebook or Python scripts to analyze the effect of noise on quantum addition.
3. Adjust noise levels and observe their effect on the output and fidelity.

## Results and Observations
- **Noise Effects**: Higher noise levels result in more incorrect measurement outcomes and lower fidelity, indicating greater deviation from the ideal quantum state.
- **Mitigating Noise**: Techniques like optimizing gate depth, applying error correction, and noise-aware compilation can be effective in reducing noise impact.
- **Gate Count Impact**: The number of gates affects noise accumulation. Circuits with fewer gates have better resilience to noise and achieve higher fidelity.

## Conclusion
This repository demonstrates how noise affects quantum computations and provides methods to mitigate its effects. It highlights the importance of optimizing quantum circuits to reduce gate count and applying noise-aware techniques to achieve accurate results in quantum computing.

For more information, feel free to reach out to the Quantum Computing Mentorship Program coordinators.

