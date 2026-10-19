# Adversarial Network Analysis: Hiding Influential Individuals & Communities

> **M.Sc. Data Science Dissertation Project**[cite: 2]
> *Author:* Siddhartha Sen (Roll No: 423)[cite: 2]
> *Supervisors:* Dr. Narayan Changder (TCG CREST, IAI) & Dr. Anal Acharya (St. Xavier's College, Kolkata)[cite: 2, 3]

---

## 📌 Project Overview
* This repository contains the research, simulation code, and analysis for my M.Sc. Data Science dissertation[cite: 2].
* The study explores the intersection of network science, graph theory, and privacy preservation[cite: 5, 6, 7].
* It addresses how key individuals ("masterminds") or tight-knit communities can conceal their structural importance in social or crime networks without completely sacrificing their network influence[cite: 5, 6, 11].
* While network analysis tools are extensively deployed for tracking viral diffusion, counter-terrorism, and fraud detection, this project approaches the problem from an adversarial/privacy-preserving perspective[cite: 5, 6, 7, 8].
* The core question investigated is whether users or communities can proactively rewire their connections to evade detection mechanisms[cite: 7, 8].

---

## 🔍 Key Concepts & Objectives
* **Centrality Minimization:** Reducing a target node's visibility across three primary centrality metrics:
  * **Degree Centrality ($C_{deg}$):** Proportional to the number of a node's direct neighbors[cite: 9].
  * **Closeness Centrality ($C_{clos}$):** Measures importance in terms of shortest distances to all other nodes[cite: 9].
  * **Betweenness Centrality ($C_{betw}$):** Quantifies how often a node lies on shortest paths between other nodes, acting as a bridge[cite: 9, 10].
* **Influence Recovery:** Utilizing diffusion models to ensure the mastermind can still project influence after rewiring:
  * **Independent Cascade (IC) Model:** Captures the probabilistic ease with which influence diffuses through the network[cite: 6, 12].
  * **Linear Threshold (LT) Model:** Captures the structural resistance of the network to influence diffusion originating from the mastermind[cite: 6, 11, 12].
* **Community Concealment:** Lowering network **modularity** to prevent community detection algorithms (like Louvain) from isolating and exposing core target groups[cite: 8, 14, 15, 20].

---

## ⚙️ Heuristics Analyzed & Implemented
The project implements, tests, and compares several state-of-the-art hiding heuristics alongside a novel proposed method:
* **ROAM (Remove One, Add Many):** Focuses on local neighborhood rewiring by disconnecting a mastermind from a key neighbor and redistributing ties to less influential neighbors[cite: 11, 15].
* **DICE (Disconnect Internally, Connect Externally):** Targets community structures by cutting internal links and bridging connections outward to drop modularity[cite: 14, 15].
* **HERMES (Hide Exposures by Removing Mastermind's External Sources):** Identifies core communities and systematically reroutes a mastermind's external connections[cite: 16, 20].
* **C3R (Community Constrained Cascade Re-routing) [Novel Heuristic]:** A multi-hop rewiring strategy proposed in this work that reroutes information flows through weak nodes in both external and core communities to challenge threat detection capabilities[cite: 20, 21].

---

## 📊 Summary of Key Findings
* Tested on benchmark networks including the **9/11 Terrorist Attack Network** (36 nodes, 64 edges) and a fragmented subset of the **SNAP Ego-Facebook Network** (333 nodes, 2978 edges)[cite: 12, 16, 19, 23].
* **Centrality Trade-offs:** Results confirm that targeted link rewiring successfully degrades the global ranking sum of mastermind nodes, making them significantly harder to spotlight via standard automated pipelines[cite: 17, 19, 21].
* **Cascade Dynamics:** Simulations consistently demonstrate a drop in IC influence values and a rise in LT structural resistance across iterations, validating theoretical expectations that influence containment increases safety from tracking[cite: 14, 19, 21].

---

## 🛠️ Tech Stack & Dependencies
* **Language:** Python[cite: 12]
* **Core Libraries:** 
  * `networkx` for graph construction, network topologies, and centrality metrics[cite: 12].
  * `matplotlib` / `seaborn` for network and simulation plotting.
  * `numpy` / `pandas` for data manipulation and numerical modeling.

---

## 📂 Repository Structure
```text
├── datasets/            # Contains network data files (e.g., 9/11 network, Facebook fragments)[cite: 12, 16, 23]
├── notebooks/           # Jupyter notebooks for heuristic simulations (ROAM, DICE, HERMES, C3R)[cite: 11, 14, 15, 16, 20]
├── scripts/             # Modular Python scripts for metric calculations and diffusion models[cite: 6, 9, 11]
├── report/              # Full M.Sc. Dissertation PDF document[cite: 2]
└── README.md            # Project documentation
