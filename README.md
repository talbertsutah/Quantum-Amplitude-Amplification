# Quantum Amplitude Amplification

This repo contains a single Jupyter notebook, QAA-and-QME.ipynb

The notebook implements algorithms for **Quantum Amplitude Estimation** (QAA) and **Quantum Mean Estimation** (QME) based on a [2021 paper by Shyamsundar](https://doi.org/10.1007/s11128-023-04146-3). 

## Quantum Amplitude Estimation

This is a generalization of the boolean quantum amplitude amplification algorithm. Recall that boolean QAA, essentially Grover's algorithm, finds marked states with high probability. The non-boolean QAA does not take as inputs only marked or unmarked sets, but allows for a ``degree of markedness'' via a non-boolean oracle $\varphi : \{ 0, 1 \}^d \to \mathbb{R}$. After a fixed number of iterations of a Grover search type operator, the algorithm returns qubits according to a well-controlled but somewhat arbitrary probability distribution. This is contrast to the Grover case, where the distribution is highly concentrated on marked states.

## Quantum Mean Estimation

For a given unitary operator $U$ and a statevector $\psi_0$, QME is an algorithm for estimating $\bra{\psi_0} U \ket{\psi_0}$. It is not strictly a new algorithm. Shyamsundar observes that the quantit can be computed using the quantum phase estimation algorithm.

## To Do

The basic algorithsm for quantum amplitude amplification and quantum mean estimation are implemented. Some improvements could be made and extensions could be carried out, which are listed here:

- Create a wrapper function that combines the QME algorithm and the QAA algorithm into one larger algorithm. Finding the optimal number of iterations $K$ for the QAA algorithm requires knowing a quantity $\cos \theta$, which is determined by the input parameters to the QAA algorithm. In the current notebook it is computed exactly for the specific input parameters. A future version should use the existing QME algorithm to estimate $\cos \theta$.
- Implement testing for the QME algorithm. However this should be trivial because it is only applying Quantum Phase Estimation.
- Apply the QAA algorithm to sample from a probability distribution. An interesting example would be for a stat mech model on graphs, like Ising or dimers.
