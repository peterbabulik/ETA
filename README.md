# ETA - Equations To Algorithms

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/peterbabulik/ETA/)

**Translating mathematical equations into quantum computing algorithms for Python programmers.**

## Overview

ETA (Equations To Algorithms) is a collection of Jupyter notebooks that bridge the gap between mathematical formalism and practical quantum computing implementations. Each notebook takes a fundamental equation from physics or mathematics and translates it into working Python code using Qiskit.

This project is designed for:
- **Python programmers** interested in quantum computing
- **Students** learning quantum mechanics and quantum algorithms
- **Researchers** looking for practical implementations of theoretical concepts

## Notebooks

### 1. Discrete Fourier Transform ([`DiscreteFourierTransform.ipynb`](DiscreteFourierTransform.ipynb))

**Equation:** $X_k = \frac{1}{\sqrt{N}} \sum_{n=0}^{N-1} x_n e^{2\pi i \frac{nk}{N}}$

**Python Analogy:** `change_basis()` - Transform from time domain to frequency domain.

**Topics Covered:**
- Quantum Fourier Transform (QFT)
- Classical FFT vs Quantum QFT complexity comparison
- Hadamard and Controlled-Phase gates
- Round-trip unit testing (QFT → Inverse QFT)

**Key Concepts:**
- $O(\log^2 N)$ quantum complexity vs $O(N \log N)$ classical
- Basis transformation: Computational → Fourier
- Binary fraction phase encoding

---

### 2. Quantum Phase Estimation ([`QuantumPhaseEstimation.ipynb`](QuantumPhaseEstimation.ipynb))

**Equation:** $U|\psi\rangle = e^{i\theta} |\psi\rangle$

**Python Analogy:** `find_phase()` - Detect the internal rotation frequency of a black-box function.

**Topics Covered:**
- Eigenvalue/eigenvector problems
- Controlled-U operations and phase kickback
- Inverse QFT for phase readout
- Applications: Shor's Algorithm, Quantum Chemistry

**Key Concepts:**
- Counting qubits for precision
- Phase kickback mechanism
- Binary phase encoding

---

### 3. Grover's Algorithm ([`GroversAlgorithm.ipynb`](GroversAlgorithm.ipynb))

**Equation:** Find $x$ such that $f(x) = 1$

**Python Analogy:** `boost_probability()` - Amplify the probability of finding the correct answer.

**Topics Covered:**
- Boolean satisfiability (SAT) problems
- Oracle construction (marks the winner)
- Diffusion operator (inverts about average)
- Amplitude amplification

**Key Concepts:**
- $O(\sqrt{N})$ quantum speedup
- Oracle-Diffuser pattern
- Optimal number of iterations

---

### 4. CHSH Circuit - Bell's Theorem ([`CHSHCircuit.ipynb`](CHSHCircuit.ipynb))

**Equation:** $S = E(a,b) - E(a,b') + E(a',b) + E(a',b') \leq 2$

**Python Analogy:** `test_reality()` - A unit test proving quantum entanglement exists.

**Topics Covered:**
- Bell's inequality and CHSH game
- Quantum entanglement
- Measurement in different bases
- Violation of classical bounds ($2\sqrt{2} \approx 2.82$)

**Key Concepts:**
- Local hidden variables vs quantum mechanics
- Entanglement verification
- Correlation measurements

---

### 5. Born Rule ([`BornRule.ipynb`](BornRule.ipynb))

**Equation:** $P(\psi_1 \to \psi_2) = |\langle\psi_1|\psi_2\rangle|^2$

**Python Analogy:** `assert_similarity()` - Measure the overlap between two quantum states.

**Topics Covered:**
- Quantum state transition probability
- Compute-Uncompute method (Inversion Test)
- Fidelity measurement between quantum states
- Alternative: Swap Test for state overlap

**Key Concepts:**
- State preparation circuits ($U_1$, $U_2$)
- Inverse operations ($U^\dagger$)
- Measurement in computational basis

---

### 6. Hamiltonian Simulation ([`Hamiltonian_Simulation.ipynb`](Hamiltonian_Simulation.ipynb))

**Equation:** $|\psi(t)\rangle = e^{-i\hat{H}t} |\psi(0)\rangle$

**Python Analogy:** `TimeEvolution()` - Simulate the time evolution of a quantum system.

**Topics Covered:**
- Schrödinger equation simulation
- Trotterization algorithm
- Ising Hamiltonian ($H = Z_0 Z_1 + X_0 + X_1$)
- Time evolution operators

**Key Concepts:**
- Breaking continuous time into discrete steps
- Gate decomposition: $e^{-iXt}$ → `Rx`, $e^{-iZZt}$ → `CX-RZ-CX`
- The "Killer App" for quantum computers (chemistry, materials science)

## Requirements

The notebooks are designed to run in:
- **Google Colab** (recommended - no installation required)
- **Local Jupyter environment**

### Dependencies

```bash
pip install qiskit qiskit-aer numpy matplotlib
```

## Project Structure

```
ETA/
├── README.md                      # This file
├── LICENSE                        # MIT License
├── prompt.md                      # Educational curriculum outline
├── DiscreteFourierTransform.ipynb # QFT implementation
├── QuantumPhaseEstimation.ipynb   # QPE implementation
├── GroversAlgorithm.ipynb         # Grover's search implementation
├── CHSHCircuit.ipynb              # Bell's theorem implementation
├── BornRule.ipynb                 # Born Rule implementation
└── Hamiltonian_Simulation.ipynb   # Schrödinger equation simulation
```

## Learning Path

For beginners, we recommend studying the notebooks in this order:

1. **Discrete Fourier Transform** - Essential subroutine for many quantum algorithms
2. **Quantum Phase Estimation** - Builds on QFT, used in Shor's algorithm
3. **Grover's Algorithm** - Fundamental search algorithm with quadratic speedup
4. **CHSH Circuit** - Demonstrates quantum advantage and entanglement
5. **Born Rule** - Fundamental measurement probability in quantum mechanics
6. **Hamiltonian Simulation** - Advanced topic with practical applications

## Complexity Comparison

| Algorithm | Classical Complexity | Quantum Complexity |
|-----------|---------------------|-------------------|
| Fourier Transform | $O(N \log N)$ | $O(\log^2 N)$ |
| Phase Estimation | $O(1/\epsilon)$ | $O(\log(1/\epsilon))$ |
| Search (SAT) | $O(N)$ | $O(\sqrt{N})$ |
| Born Rule (Fidelity) | $O(2^n)$ | $O(n)$ |
| Hamiltonian Simulation | Exponential | Polynomial |

## Key Features

- **Equation-First Approach**: Each notebook starts with the mathematical equation
- **Step-by-Step Translation**: Clear explanation of how math becomes code
- **Working Examples**: Executable code with real outputs
- **Circuit Diagrams**: Visual representation of quantum circuits
- **Theoretical Validation**: Comparison of measured vs theoretical results

## Contributing

Contributions are welcome! If you have suggestions for new equations to translate or improvements to existing notebooks, please open an issue or submit a pull request.

## License

This project is licensed under the MIT License - see the [`LICENSE`](LICENSE) file for details.

## Author

**peterbabulik**

---

*Star this repository if you find it useful!*
