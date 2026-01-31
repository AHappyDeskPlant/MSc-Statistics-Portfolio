# MALA and Ising Model Sampling

This project explores advanced Monte Carlo simulation techniques, focusing on the efficiency of the **Metropolis-Adjusted Langevin Algorithm (MALA)** compared to **Random Walk Metropolis-Hastings (RWMH)** in high dimensions. Additionally, it investigates sampling dynamics for the **Ising Model** using both Systematic-Scan Gibbs Sampling and single-flip Metropolis-Hastings.

## Project Overview

The analysis is divided into two primary sections:

1.  **High-Dimensional Sampling (Multivariate Normal):**
    * Implementation of RWMH and MALA to target a standard multivariate normal distribution.
    * Investigation of optimal scaling parameters ($l$) across varying dimensions ($p=1$ to $p=100$).
    * Comparison of mixing efficiency using Mean Squared Jump Distance (MSJD).

2.  **Discrete State Space Sampling (Ising Model):**
    * Implementation of a Systematic-Scan Gibbs Sampler on a $5 \times 5$ grid.
    * Analysis of the interaction parameter ($J$) and its effect on mixing and phase transitions.
    * Derivation and implementation of a single-flip Metropolis-Hastings algorithm, proving detailed balance for a deterministic flip proposal.

## Algorithms Implemented

### 1. Random Walk Metropolis-Hastings (RWMH)
A standard random walk implementation targeting $\mathcal{N}(\mathbf{0}, \mathbf{I}_p)$.
* **Key Finding:** Confirms theoretical optimal scaling of $l \approx 2.38$ for dimensions $p \ge 5$.
* **Key Finding:** Acceptance rate converges to $\approx 0.234$ at the optimum.

### 2. Metropolis-Adjusted Langevin Algorithm (MALA)
MALA incorporates gradient information to guide the proposal towards regions of higher probability density.
* **Derivation:** Includes the mathematical derivation of the acceptance probability $\alpha(Y|X)$ using the Langevin diffusion drift term.
* **Key Finding:** MALA significantly outperforms RWMH in high dimensions ($p=100$), yielding an MSJD almost 30 times larger.
* **Key Finding:** Optimal scaling observed at $l \approx 1.7$ with an acceptance rate of $\approx 0.574$.

### 3. Ising Model (Gibbs & MH)
Simulation of ferromagnetic spin systems.
* **Gibbs Sampler:** Demonstrates rapid mixing at low $J$ (0.05) and "sticky" behavior/multimodality at high $J$ (0.5, 1.0).
* **Metropolis-Hastings:** Justifies a deterministic bit-flip proposal ($q(x'|x) = 1$) via symmetry and detailed balance.
* **Comparison:** Both methods exhibit similar path-dependence limitations at high interaction strengths.

## Dependencies

To run the run the `Rmd` file please use the below

```{r}
rmarkdown::render("mcm_mala_ising/mala_ising.Rmd")
```