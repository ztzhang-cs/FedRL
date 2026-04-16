# FedRL: Federated Reinforcement Learning with Attention for Bottleneck-Aware SFC Orchestration

[![Status](https://img.shields.io/badge/Status-Under_Review-orange.svg)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)]()

> **Official PyTorch Implementation** for the paper: *"FedRL: Federated Reinforcement Learning with Attention for Bottleneck-Aware SFC Orchestration"*. (Currently under review at IEEE JCC 2026).

## 📖 Overview

Network Function Virtualization (NFV) facilitates the dynamic instantiation of Virtual Network Functions (VNFs) into Service Function Chains (SFCs). However, centralized orchestration faces severe privacy concerns and scalability limits, while existing distributed heuristics fail to explicitly discover structural network bottlenecks.

To bridge this gap, we propose a **two-level federated reinforcement learning (FedRL) framework**:
* **Macroscopic Routing (Global Level):** A penalty-aware bandit agent selects inter-domain paths to circumvent congestion without exposing raw topological data.
* **Microscopic Placement (Domain Level):** Parallel local orchestrators utilize Attention Policy Gradients (Attention PG) to capture relational dependencies and proactively evade saturated servers.
* **Federated Synchronization:** A performance-weighted aggregation protocol securely synchronizes anti-congestion intelligence across domains.

**Key Results:** Our approach autonomously learns to detour traffic away from congested choke points, achieving a maximum **service acceptance ratio of 84.25%** and minimizing the average **end-to-end delay to 212.29 ms**.

## 🚀 Getting Started

### 1. Prerequisites & Installation

Clone the repository to your local machine:
```bash
git clone [https://github.com/ztzhang-cs/FedRL-SFC.git](https://github.com/ztzhang-cs/FedRL-SFC.git)
cd FedRL-SFC
```

Create and activate a Python virtual environment, then install the required dependencies.

**For Windows (PowerShell):**
```powershell
.\venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

**For Linux / macOS:**
```bash
source venv/bin/activate
pip install -r requirements.txt
```

### 2. Running the Experiments

The framework is evaluated across two distinct topological scenarios:
* **Toy Environment:** A 6-domain structured network engineered with severe asymmetric bottlenecks.
* **Random Environment:** A 12-domain complex, procedurally generated multi-domain mesh network.

To train the FedRL framework, execute the following commands based on your target environment:

**Evaluate on the Toy Environment:**
```bash
python -m experiments.run_experiments --mode toy
```

**Evaluate on the Random Environment:**
```bash
python -m experiments.run_experiments --mode random
```

## 📊 Reproducibility Statement

Due to the inherent stochasticity of Deep Reinforcement Learning (DRL) algorithms and the dynamic generation of network traffic requests, training the framework from scratch without fixed random seeds may yield slight variance in convergence and performance metrics.


## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
