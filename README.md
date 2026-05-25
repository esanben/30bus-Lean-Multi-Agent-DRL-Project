# 30-Bus Lean Multi-Agent DRL Framework for Networked Microgrid Energy Management Under Uncertainty

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Paper DOI](https://img.shields.io/badge/DOI-10.1016%2Fj.apenergy.2026.127354-blue)](https://doi.org/10.1016/j.apenergy.2026.127354)
[![Research Area](https://img.shields.io/badge/Research-Microgrid%20Energy%20Management-green)](#project-overview)
[![Method](https://img.shields.io/badge/Method-Multi--Agent%20DRL-purple)](#methodological-framework)

This repository contains the code and data assets for a **30-bus networked microgrid energy management study under renewable generation and load demand uncertainties**. The project implements a Lean Multi-Agent Deep Reinforcement Learning (L-MADRL) framework in which learning agents support day-ahead scheduling decisions, while an optimization-based evaluation layer preserves operational feasibility, market coordination, and network security.

<p align="center">
  <img src="https://github.com/user-attachments/assets/2dd56039-7c94-4259-b168-cde0fdbbc47d" alt="Lean multi-agent DRL framework for networked microgrid energy management" width="900">
</p>

---

## Project Overview

Networked microgrids require coordinated scheduling across multiple decision-making entities, including electricity retailers, microgrids, distributed generators, storage assets, and network interfaces. The problem becomes more challenging when renewable generation and load demand are uncertain, because schedules must remain economically efficient and technically feasible under changing operating conditions.

This project addresses that challenge using a **lean multi-agent DRL and optimization framework**. The DRL layer learns useful decision policies from uncertain operating states, while the optimization layer evaluates the actions using physical, economic, and network-aware constraints.

This repository focuses on:

1. **30-bus networked microgrid modeling**: Representing a networked microgrid environment with multiple electricity retailers and microgrids.
2. **Uncertainty-aware energy management**: Incorporating renewable generation and load uncertainty into day-ahead scheduling.
3. **Lean multi-agent DRL decision-making**: Using multiple learning agents to guide scheduling actions without forcing the neural networks to directly enforce every operational constraint.
4. **Optimization-based feasibility evaluation**: Reformulating the lower-level microgrid optimization problem using Karush-Kuhn-Tucker conditions and evaluating selected actions through a single-level mathematical program.
5. **Benchmark comparison**: Organizing deterministic optimization, stochastic optimization, and DRL-based solution assets for comparative analysis.

---

## Important Links and Tools

- [Full Paper](https://doi.org/10.1016/j.apenergy.2026.127354)
- [Python](https://www.python.org/downloads/)
- [Jupyter Notebook](https://jupyter.org/)
- [NumPy](https://numpy.org/)
- [pandas](https://pandas.pydata.org/)
- [Matplotlib](https://matplotlib.org/)

> Note: The exact package versions and solver dependencies should be checked inside the extracted project archives. The deterministic, stochastic, and optimization-based evaluation models may require a compatible mathematical optimization solver or modeling environment.

---

## Project Requirements

### Objective

Develop and organize a 30-bus networked microgrid energy management framework that combines **multi-agent deep reinforcement learning** with **optimization-based feasibility checking** for day-ahead scheduling under renewable and load uncertainties.

### Specifications

- **System Scope**: Modified 30-bus networked microgrid case with electricity retailers, microgrids, and network constraints.
- **Uncertainty Sources**: Renewable generation and load demand variations.
- **Learning Method**: Lean Multi-Agent Deep Reinforcement Learning, implemented through a multi-agent Deep Q-Network formulation.
- **Optimization Layer**: Single-level reformulation of a bi-level energy management problem using Karush-Kuhn-Tucker optimality conditions.
- **Network Security**: Inclusion of available transfer capability and generation shift factor values to support network-aware power exchange.
- **Benchmarks**: Deterministic and stochastic optimization cases for comparison against the DRL-based approach.
- **Documentation**: Clear repository-level documentation for researchers, students, and practitioners interested in DRL-enabled power system energy management.

---

## Research Context

The methodology builds on the following peer-reviewed publication:

> Ayodele Benjamin Esan, Hussain Shareef, Ahmad K. ALAhmad,  
> **Lean multi-agent deep reinforcement learning for uncertainty handling in the energy management of networked microgrids**,  
> *Applied Energy*, Volume 408, 2026, Article 127354.  
> DOI: [10.1016/j.apenergy.2026.127354](https://doi.org/10.1016/j.apenergy.2026.127354)

The paper develops a Lean Multi-Agent Deep Reinforcement Learning framework for networked microgrid energy management under uncertainty. In the published framework, a multi-agent Deep Q-Network is integrated with a single-level reformulation of a bi-level optimization problem. The upper level represents electricity retailer objectives and network transfer capability, while the lower-level microgrid cost minimization problem is replaced by Karush-Kuhn-Tucker conditions to support tractable feasibility evaluation.

This repository provides the **30-bus project implementation assets** associated with that research direction, including DRL code and data, deterministic optimization code, stochastic optimization code, generation shift factor values, and supplementary electricity retailer and microgrid parameters.

---

## Methodological Framework

The project combines data-driven learning, optimization, and power system modeling.

### 1. Data and Parameter Preparation

Input data and supplementary parameter files define the networked microgrid environment, electricity retailer parameters, microgrid parameters, generation units, demand profiles, uncertainty representations, and network sensitivity data.

### 2. Networked Microgrid Formulation

The system is modeled as a coordinated network of electricity retailers and microgrids. Electricity retailers seek profitable and secure energy exchanges, while microgrids seek cost-effective operation subject to generation, storage, demand, ramping, exchange, and network constraints.

### 3. Markov Decision Process Design

The energy management problem is mapped into a reinforcement learning structure:

| Component | Interpretation in this project |
|:---|:---|
| **State** | Operating condition of the networked microgrid, including uncertain renewable and demand information. |
| **Action** | DRL-selected control guidance, action bounds, or transformed stochastic parameters used by the optimization layer. |
| **Reward** | Economic and technical feedback based on cost, profit, feasibility, and network-aware scheduling performance. |
| **Environment** | The networked microgrid system and optimization layer used to evaluate actions. |
| **Policy** | The learned mapping from system states to scheduling-support actions. |

### 4. Lean Multi-Agent DRL Layer

Multiple learning agents interact with the networked microgrid environment. The lean design reduces the direct burden on the neural networks by allowing the optimization layer to enforce detailed physical and market constraints. This improves practical interpretability and helps the agents focus on learning high-value decision guidance under uncertainty.

### 5. Single-Level Optimization and Feasibility Layer

The lower-level microgrid optimization problem is reformulated using Karush-Kuhn-Tucker conditions. This converts the original bi-level energy management problem into a single-level mathematical program with equilibrium constraints. The resulting formulation is used to evaluate DRL actions and return reward or penalty feedback.

### 6. Network-Aware Coordination

Available transfer capability and generation shift factor information are used to account for network limits and power transfer effects. This enables the framework to evaluate schedules not only by cost and profit, but also by their network security and transfer feasibility.

### 7. Benchmarking

The DRL-based approach is compared with deterministic and stochastic optimization benchmarks. This supports a structured evaluation of operating cost, electricity retailer profit, available transfer capability, power exchange behavior, and computational performance.

---

## Key Concepts

| Term | Meaning |
|:---|:---|
| **NMG** | Networked microgrid system containing interconnected microgrids and electricity retailers. |
| **MG** | Microgrid with local demand, distributed energy resources, storage, and operational constraints. |
| **ER** | Electricity retailer that participates in energy exchange and market coordination. |
| **L-MADRL** | Lean Multi-Agent Deep Reinforcement Learning framework for coordinated decision-making. |
| **L-MADQN** | Deep Q-Network based implementation of the lean multi-agent DRL framework. |
| **ATC** | Available Transfer Capability, used to support secure network-aware power exchange. |
| **GSF** | Generation Shift Factor values used to represent network flow sensitivities. |
| **KKT** | Karush-Kuhn-Tucker conditions used to reformulate the lower-level optimization problem. |
| **MPEC** | Mathematical Program with Equilibrium Constraints derived from the KKT-based reformulation. |

---

## Repository Structure

The repository is organized as compressed project archives. Extract the files before running the models.

```text
30bus-Lean-Multi-Agent-DRL-Project
├── DRL codes and data 30 bus.zip                  # Multi-agent DRL implementation and 30-bus case data
├── Deterministic code with data.zip               # Deterministic optimization benchmark and input data
├── Stochastic optimization code with data.zip     # Stochastic optimization benchmark and input data
├── GSF values.zip                                 # Generation shift factor values for network constraints
├── Supplementary materials (ER and MG parameters).zip
│                                                  # Electricity retailer and microgrid parameter files
├── LICENSE                                        # MIT License
└── README.md                                      # Project overview, setup, and documentation
```

A clean extracted working structure is recommended:

```text
30bus-Lean-Multi-Agent-DRL-Project
├── drl_case
├── deterministic_case
├── stochastic_case
├── gsf_values
├── supplementary_materials
├── LICENSE
└── README.md
```

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/esanben/30bus-Lean-Multi-Agent-DRL-Project.git
cd 30bus-Lean-Multi-Agent-DRL-Project
```

### 2. Extract the Project Archives

```bash
unzip "Supplementary materials (ER and MG parameters).zip" -d supplementary_materials
unzip "GSF values.zip" -d gsf_values
unzip "Deterministic code with data.zip" -d deterministic_case
unzip "Stochastic optimization code with data.zip" -d stochastic_case
unzip "DRL codes and data 30 bus.zip" -d drl_case
```

### 3. Prepare the Environment

Review the scripts, notebooks, and model files inside each extracted archive, then install the required packages. A typical environment for this type of project may include:

```bash
python -m venv .venv
source .venv/bin/activate
pip install numpy pandas scipy matplotlib jupyter
```

Depending on the implementation files inside the archives, you may also need:

- A deep learning library used by the DRL scripts.
- A mathematical programming solver compatible with the deterministic, stochastic, or single-level optimization models.
- A notebook environment or IDE for running experiments and reviewing outputs.

### 4. Recommended Execution Order

1. Extract the supplementary ER and MG parameter files.
2. Extract the GSF files and confirm that network sensitivity data are available.
3. Run the deterministic optimization benchmark.
4. Run the stochastic optimization benchmark.
5. Train and test the L-MADRL or L-MADQN model using the DRL archive.
6. Compare operating cost, electricity retailer profit, available transfer capability, power exchange, and computational performance.

---

## Expected Outputs

The project archives may generate the following outputs depending on the scripts executed:

- Day-ahead schedules for electricity retailers and microgrids.
- Microgrid operating cost profiles.
- Electricity retailer profit profiles.
- Power exchange schedules among network participants.
- Available transfer capability profiles.
- Network feasibility and security indicators.
- DRL training and testing performance metrics.
- Comparative results for deterministic, stochastic, and DRL-based approaches.

---

## Evaluation Metrics

The following metrics are useful for analyzing and comparing results:

| Metric | Purpose |
|---|---|
| **MG operating cost** | Measures economic performance from the microgrid perspective. |
| **ER profit** | Measures market performance from the electricity retailer perspective. |
| **ATC profile** | Evaluates secure transfer capability across the network. |
| **Power exchange schedule** | Tracks energy transactions between retailers and microgrids. |
| **Constraint feasibility** | Confirms satisfaction of generation, ramping, exchange, and network constraints. |
| **Runtime** | Measures computational efficiency and scalability. |
| **Training reward** | Tracks DRL learning progress across episodes. |

---

## Academic Contribution

This project contributes to the growing body of research on intelligent and optimization-aware energy management for modern power systems. Its core contribution is the integration of a **lean multi-agent DRL decision layer** with a **mathematical programming feasibility layer**.

This structure is useful because it:

1. Reduces the complexity handled directly by learning agents.
2. Preserves physical and market constraints through optimization.
3. Supports uncertainty-aware scheduling under renewable and load variations.
4. Enables coordinated decision-making among multiple energy entities.
5. Provides a structured basis for comparison with deterministic and stochastic optimization methods.

---

## Notes on Reproducibility

For reproducible experiments, keep the extracted folders in a consistent structure and document all changes made to file paths or solver settings.

Recommended reproducibility records include:

- Python version or programming environment version.
- Package versions.
- Solver name and solver version.
- Random seeds used during DRL training.
- Training episodes, batch size, learning rate, and discount factor.
- Hardware details, including CPU and GPU information.
- Date and configuration of each experiment.

---

## Citation

If this repository, codebase, or methodology supports your research, please cite the associated paper:

```bibtex
@article{Esan2026LeanMADRL,
  title   = {Lean multi-agent deep reinforcement learning for uncertainty handling in the energy management of networked microgrids},
  author  = {Esan, Ayodele Benjamin and Shareef, Hussain and ALAhmad, Ahmad K.},
  journal = {Applied Energy},
  volume  = {408},
  pages   = {127354},
  year    = {2026},
  doi     = {10.1016/j.apenergy.2026.127354}
}
```

---

## License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute the code, provided that the original copyright and license notice are retained.

---

## About Me

I am **Ayodele Benjamin Esan**. I hold a doctorate in Electrical Engineering with a focus on Deep Reinforcement Learning applications in Energy Systems. I am interested in building intelligent, data-driven, and optimization-aware systems for modern power and energy applications.

Feel free to connect with me on:

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ayodele-benjamin-esan-ph-d-03b948106)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/esanben)
[![Medium](https://img.shields.io/badge/Medium-000000?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@esanayodele.benjamin)
