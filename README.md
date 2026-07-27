# Approximating $\pi$ using the Monte Carlo Method

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21629499.svg)](https://doi.org/10.5281/zenodo.21629499)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/)

This repository contains the Python implementation and the academic paper focused on the stochastic estimation of the mathematical constant $\pi$ via the **Monte Carlo Method** (based on a geometric model of random points inscribed within a square).

📄 **Read the full paper published on Zenodo:** [Approximating $\pi$ using the Monte Carlo Method (DOI)](https://zenodo.org/records/21629499) *(Replace this link with your actual DOI URL)*

---

## 📌 Project Overview

The project explores how **geometric probability** and the **Law of Large Numbers** allow us to approximate constant values through stochastic simulations.

1. Uniformly distributed random points $(x, y)$ are generated within a square of side length $2r$ ($[-1, 1] \times [-1, 1]$).
2. The Euclidean distance ($x^2 + y^2 \le 1$) determines whether each point falls inside the inscribed circle of radius $r=1$.
3. The ratio of the areas provides the estimate for $\pi$:
   $$\frac{A_{\text{circle}}}{A_{\text{square}}} = \frac{\pi r^2}{4 r^2} = \frac{\pi}{4} \implies \hat{\pi} = 4 \cdot \frac{N_{\text{inside}}}{N_{\text{total}}}$$

### 📉 Convergence Rate
The analysis confirms that the Standard Error (SE) decreases according to the theoretical limit $\mathcal{O}\left(\frac{1}{\sqrt{N}}\right)$, requiring an exponential increase in sample size to gain additional decimal precision.

---

## 📊 Key Results ($N = 1,000,000$)

| Metric | Value |
| :--- | :--- |
| **Total Points ($N$)** | $1,000,000$ |
| **Points Inside Circle** | $785,685$ |
| **Approximated $\pi$ ($\hat{\pi}$)** | **$3.142740$** |
| **True Value ($\pi$)** | $3.141593$ |
| **Absolute Error** | $0.001147$ |
| **$3\sigma$ Interval ($99.73\%$ confidence)** | $[3.137816, 3.147664]$ |

---

## 🎨 Generated Visualizations

The script automatically generates two high-resolution figures (`300 DPI`):

1. **`Circumference.png`**: Spatial distribution of points (green = inside, red = outside).
2. **`Error_Decay.png`**: Log-log plot demonstrating the observed error convergence against the theoretical $1\sigma$ boundary.

---

## 🚀 Installation & Usage

### Prerequisites
Ensure you have Python 3.8 or higher installed along with the required libraries:

```bash
pip install numpy matplotlib
