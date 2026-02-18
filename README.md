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

### Core Algorithms

#### 1. Discrete Fourier Transform ([`DiscreteFourierTransform.ipynb`](DiscreteFourierTransform.ipynb))

**Equation:** $X_k = \frac{1}{\sqrt{N}} \sum_{n=0}^{N-1} x_n e^{2\pi i \frac{nk}{N}}$

**Python Analogy:** `change_basis()` - Transform from time domain to frequency domain.

**Topics Covered:**
- Quantum Fourier Transform (QFT)
- Classical FFT vs Quantum QFT complexity comparison
- Hadamard and Controlled-Phase gates
- Round-trip unit testing (QFT $\to$ Inverse QFT)

---

#### 2. Quantum Phase Estimation ([`QuantumPhaseEstimation.ipynb`](QuantumPhaseEstimation.ipynb))

**Equation:** $U|\psi\rangle = e^{i\theta} |\psi\rangle$

**Python Analogy:** `find_phase()` - Detect the internal rotation frequency of a black-box function.

**Topics Covered:**
- Eigenvalue/eigenvector problems
- Controlled-U operations and phase kickback
- Inverse QFT for phase readout
- Applications: Shor's Algorithm, Quantum Chemistry

---

#### 3. Grover's Algorithm ([`GroversAlgorithm.ipynb`](GroversAlgorithm.ipynb))

**Equation:** Find $x$ such that $f(x) = 1$

**Python Analogy:** `boost_probability()` - Amplify the probability of finding the correct answer.

**Topics Covered:**
- Boolean satisfiability (SAT) problems
- Oracle construction (marks the winner)
- Diffusion operator (inverts about average)
- Amplitude amplification

---

#### 4. CHSH Circuit - Bell's Theorem ([`CHSHCircuit.ipynb`](CHSHCircuit.ipynb))

**Equation:** $S = E(a,b) - E(a,b') + E(a',b) + E(a',b') \leq 2$

**Python Analogy:** `test_reality()` - A unit test proving quantum entanglement exists.

**Topics Covered:**
- Bell's inequality and CHSH game
- Quantum entanglement
- Measurement in different bases
- Violation of classical bounds ($2\sqrt{2} \approx 2.82$)

---

#### 5. Born Rule ([`BornRule.ipynb`](BornRule.ipynb))

**Equation:** $P(\psi_1 \to \psi_2) = |\langle\psi_1|\psi_2\rangle|^2$

**Python Analogy:** `assert_similarity()` - Measure the overlap between two quantum states.

**Topics Covered:**
- Quantum state transition probability
- Compute-Uncompute method (Inversion Test)
- Fidelity measurement between quantum states
- Alternative: Swap Test for state overlap

---

#### 6. Hamiltonian Simulation ([`Hamiltonian_Simulation.ipynb`](Hamiltonian_Simulation.ipynb))

**Equation:** $|\psi(t)\rangle = e^{-i\hat{H}t} |\psi(0)\rangle$

**Python Analogy:** `TimeEvolution()` - Simulate the time evolution of a quantum system.

**Topics Covered:**
- Schrödinger equation simulation
- Trotterization algorithm
- Ising Hamiltonian ($H = Z_0 Z_1 + X_0 + X_1$)
- Time evolution operators

---

### Advanced Algorithms

#### 7. Variational Quantum Eigensolver ([`VariationalQuantumEigensolver.ipynb`](VariationalQuantumEigensolver.ipynb))

**Equation:** $E(\psi) = \langle\psi|H|\psi\rangle \geq E_0$

**Python Analogy:** `find_ground_state()` - Find the minimum energy configuration using hybrid quantum-classical optimization.

**Topics Covered:**
- Rayleigh-Ritz variational principle
- Parameterized quantum circuits (ansatz)
- Hybrid quantum-classical optimization
- Applications: Quantum chemistry, drug discovery

---

#### 8. HHL Algorithm ([`HHLAlgorithm.ipynb`](HHLAlgorithm.ipynb))

**Equation:** $A|x\rangle = |b\rangle$

**Python Analogy:** `solve_linear_system()` - Solve linear equations exponentially faster for sparse matrices.

**Topics Covered:**
- Linear system solving
- Quantum phase estimation for eigenvalue decomposition
- Controlled rotation for eigenvalue inversion
- Applications: Machine learning, differential equations

---

#### 9. Deutsch-Jozsa Algorithm ([`DeutschJozsa.ipynb`](DeutschJozsa.ipynb))

**Equation:** $f: \{0,1\}^n \to \{0,1\}$ (constant or balanced?)

**Python Analogy:** `classify_function()` - Determine if function is constant or balanced in 1 query vs $2^{n-1}+1$ classically.

**Topics Covered:**
- First quantum advantage demonstration
- Phase kickback mechanism
- Quantum interference
- Foundation for more complex algorithms

---

#### 10. Quantum Teleportation ([`QuantumTeleportation.ipynb`](QuantumTeleportation.ipynb))

**Equation:** $|\psi\rangle_{Alice} \to |\psi\rangle_{Bob}$

**Python Analogy:** `transfer_state()` - Transfer quantum state using entanglement and classical communication.

**Topics Covered:**
- Bell state preparation
- Bell measurement
- Classical control operations
- No-cloning theorem implications

---

#### 11. BB84 Key Distribution ([`BB84KeyDistribution.ipynb`](BB84KeyDistribution.ipynb))

**Equation:** $K_{shared} = K_{Alice} \cap K_{Bob}$

**Python Analogy:** `generate_secure_key()` - Create provably secure shared secret key.

**Topics Covered:**
- Quantum key distribution protocol
- Eavesdropper detection via error rate
- Basis reconciliation
- Unconditional security from physics

---

## Requirements

The notebooks are designed to run in:
- **Google Colab** (recommended - no installation required)
- **Local Jupyter environment**

### Dependencies

```bash
pip install qiskit qiskit-aer numpy matplotlib
```

## Learning Path

For beginners, we recommend studying the notebooks in this order:

1. **Deutsch-Jozsa** - Simplest demonstration of quantum advantage
2. **Discrete Fourier Transform** - Essential subroutine for many algorithms
3. **Quantum Phase Estimation** - Builds on QFT, used in Shor's algorithm
4. **Grover's Algorithm** - Fundamental search algorithm
5. **CHSH Circuit** - Demonstrates quantum advantage and entanglement
6. **Born Rule** - Fundamental measurement probability
7. **Quantum Teleportation** - Quantum communication protocol
8. **BB84 Key Distribution** - Quantum cryptography
9. **Hamiltonian Simulation** - Advanced topic with practical applications
10. **Variational Quantum Eigensolver** - Near-term quantum computing
11. **HHL Algorithm** - Advanced linear algebra

## Complexity Comparison

| Algorithm | Classical Complexity | Quantum Complexity |
|-----------|---------------------|-------------------|
| Fourier Transform | $O(N \log N)$ | $O(\log^2 N)$ |
| Phase Estimation | $O(1/\epsilon)$ | $O(\log(1/\epsilon))$ |
| Search (SAT) | $O(N)$ | $O(\sqrt{N})$ |
| Born Rule (Fidelity) | $O(2^n)$ | $O(n)$ |
| Hamiltonian Simulation | Exponential | Polynomial |
| Linear Systems (HHL) | $O(N)$ | $O(\log N)$ |
| Deutsch-Jozsa | $O(2^{n-1})$ | $O(1)$ |

## Python Developer Mapping

| Equation | Python Analogy | Notebook |
|----------|---------------|----------|
| Fourier Transform | `change_basis()` | [`DiscreteFourierTransform.ipynb`](DiscreteFourierTransform.ipynb) |
| Eigenvalue Problem | `find_phase()` | [`QuantumPhaseEstimation.ipynb`](QuantumPhaseEstimation.ipynb) |
| Search/SAT | `boost_probability()` | [`GroversAlgorithm.ipynb`](GroversAlgorithm.ipynb) |
| Bell's Theorem | `test_reality()` | [`CHSHCircuit.ipynb`](CHSHCircuit.ipynb) |
| Born Rule | `assert_similarity()` | [`BornRule.ipynb`](BornRule.ipynb) |
| Schrödinger Eq | `TimeEvolution()` | [`Hamiltonian_Simulation.ipynb`](Hamiltonian_Simulation.ipynb) |
| Variational Principle | `find_ground_state()` | [`VariationalQuantumEigensolver.ipynb`](VariationalQuantumEigensolver.ipynb) |
| Linear Systems | `solve_linear_system()` | [`HHLAlgorithm.ipynb`](HHLAlgorithm.ipynb) |
| Function Classification | `classify_function()` | [`DeutschJozsa.ipynb`](DeutschJozsa.ipynb) |
| State Transfer | `transfer_state()` | [`QuantumTeleportation.ipynb`](QuantumTeleportation.ipynb) |
| Key Exchange | `generate_secure_key()` | [`BB84KeyDistribution.ipynb`](BB84KeyDistribution.ipynb) |

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
