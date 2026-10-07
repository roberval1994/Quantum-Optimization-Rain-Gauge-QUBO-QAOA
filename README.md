# Quantum Optimization of Rain-Gauge Networks (QUBO / QAOA)

**Formulating rain-gauge facility location as a QUBO and solving it with QAOA, benchmarked against classical solvers**

🌐 **Language / Idioma:** **English** | [Português](README.pt-BR.md)

---

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Qiskit](https://img.shields.io/badge/Qiskit-6929C4.svg?logo=qiskit&logoColor=white)](https://www.ibm.com/quantum/qiskit)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/status-research-blueviolet.svg)]()

> Part of the PhD research in Operational Research at **UNIFESP / ITA**.
> See the research overview: [PhD-Research-Operational-Research](https://github.com/roberval1994).

## Overview

This project formulates the **optimal placement of rain-gauge stations** as a
**Quadratic Unconstrained Binary Optimization (QUBO)** problem and solves it with the
**Quantum Approximate Optimization Algorithm (QAOA)**, comparing the results against
classical exact and heuristic solvers.

The study investigates whether quantum-inspired and quantum optimization can match or
approach classical solutions on a real spatial facility-location problem.

## Approach

1. **Problem modelling** — the covering/placement problem is encoded as a QUBO, with a penalty-based reformulation of the coverage constraints.
2. **Calibration** — the penalty coefficient (`λ`) is calibrated so that feasible solutions dominate the energy landscape.
3. **Quantum solver** — QAOA executed via **Qiskit** (simulator and/or IBM Quantum backends), with analysis of the QAOA depth/threshold behaviour.
4. **Classical baselines** — exact and heuristic solvers (including IDW-based grid processing) for comparison.
5. **Benchmark** — solver comparison on quality, scalability, and runtime.

## Repository structure

```
.
├── notebooks/
│   ├── QUBO_Rain_Gauge_Optimization.ipynb    # Main QUBO/QAOA pipeline (latest version)
│   └── celulas_amclp_analise.ipynb           # AMCLP cell-level analysis
├── data/                                     # Monthly datasets, population raster, shapefiles
├── results/                                  # Comparison tables (.csv/.xlsx), solver results
├── figures/                                  # Calibration, scalability, QAOA threshold, maps
├── requirements.txt
├── LICENSE
├── README.md                                 # English (this file)
└── README.pt-BR.md                           # Portuguese
```

## Data

> **Heavy datasets** (e.g. the ~457 MB WorldPop population raster) are **not versioned**
> in this repository. See [`data/README.md`](data/README.md) for download instructions,
> sources (WorldPop, GeoSanja/SJC, PlugField), and the expected folder layout.

## Getting started

```bash
git clone https://github.com/roberval1994/Quantum-Optimization-Rain-Gauge-QUBO-QAOA.git
cd Quantum-Optimization-Rain-Gauge-QUBO-QAOA

python -m venv .venv
.venv\Scripts\activate          # Windows
# source .venv/bin/activate     # Linux / macOS
pip install -r requirements.txt

jupyter notebook
```

> Running on real IBM Quantum hardware requires a free
> [IBM Quantum](https://quantum.ibm.com/) account and API token. The notebooks also run
> on the local Qiskit Aer simulator.

## Key results

- End-to-end QUBO formulation of a real rain-gauge placement problem.
- `λ` penalty calibration ensuring feasibility.
- Classical vs quantum solver comparison (quality, scalability, runtime).
- Reproducible figures: calibration curve, scalability, QAOA threshold, comparative maps.

## Tech stack

`Python` · `Qiskit` · `IBM Quantum` · `NumPy` · `pandas` · `GeoPandas` · `Matplotlib` · `Folium`

## Author

**Roberval Gonçalves Moreira Filho**
Data Scientist | Operational Research Analyst — PhD candidate, UNIFESP/ITA

[![Email](https://img.shields.io/badge/Email-roberval.researcher.or%40outlook.com-red)](mailto:roberval.researcher.or@outlook.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-robervalOr-blue)](https://www.linkedin.com/in/robervalOr)
[![GitHub](https://img.shields.io/badge/GitHub-roberval1994-black)](https://github.com/roberval1994)

## License

Released under the MIT License. See [LICENSE](LICENSE).
