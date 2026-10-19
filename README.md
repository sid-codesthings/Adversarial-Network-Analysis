# Adversarial Network Analysis: Hiding Influential Individuals & Communities

> **M.Sc. Data Science Dissertation Project**
> *Author:* Siddhartha Sen (Roll No: 423)
> *Supervisors:* Dr. Narayan Changder (TCG CREST, IAI) & Dr. Anal Acharya (St. Xavier's College, Kolkata)

---

## 📌 Project Overview
* This repository contains the research, simulation code, and analysis for my M.Sc. Data Science dissertation.
* The study explores the intersection of network science, graph theory, and privacy preservation.
* It addresses how key individuals ("masterminds") or tight-knit communities can conceal their structural importance in social or crime networks without completely sacrificing their network influence.
* While network analysis tools are extensively deployed for tracking viral diffusion, counter-terrorism, and fraud detection, this project approaches the problem from an adversarial/privacy-preserving perspective.
* The core question investigated is whether users or communities can proactively rewire their connections to evade detection mechanisms.

---

## 🔍 Key Concepts & Objectives
* **Centrality Minimization:** Reducing a target node's visibility across three primary centrality metrics:
  * **Degree Centrality ($C_{deg}$):** Proportional to the number of a node's direct neighbors.
  * **Closeness Centrality ($C_{clos}$):** Measures importance in terms of shortest distances to all other nodes.
  * **Betweenness Centrality ($C_{betw}$):** Quantifies how often a node lies on shortest paths between other nodes, acting as a bridge.
* **Influence Recovery:** Utilizing diffusion models to ensure the mastermind can still project influence after rewiring:
  * **Independent Cascade (IC) Model:** Captures the probabilistic ease with which influence diffuses through the network.
  * **Linear Threshold (LT) Model:** Captures the structural resistance of the network to influence diffusion originating from the mastermind.
* **Community Concealment:** Lowering network **modularity** to prevent community detection algorithms (like Louvain) from isolating and exposing core target groups.

---

## ⚙️ Heuristics Analyzed & Implemented
The project implements, tests, and compares several state-of-the-art hiding heuristics alongside a novel proposed method:
* **ROAM (Remove One, Add Many):** Focuses on local neighborhood rewiring by disconnecting a mastermind from a key neighbor and redistributing ties to less influential neighbors.
* **DICE (Disconnect Internally, Connect Externally):** Targets community structures by cutting internal links and bridging connections outward to drop modularity.
* **HERMES (Hide Exposures by Removing Mastermind's External Sources):** Identifies core communities and systematically reroutes a mastermind's external connections.
* **C3R (Community Constrained Cascade Re-routing) [Novel Heuristic]:** A multi-hop rewiring strategy proposed in this work that reroutes information flows through weak nodes in both external and core communities to challenge threat detection capabilities.

---

## 📊 Summary of Key Findings
* Tested on benchmark networks including the **9/11 Terrorist Attack Network** (36 nodes, 64 edges) and a fragmented subset of the **SNAP Ego-Facebook Network** (333 nodes, 2978 edges).
* **Centrality Trade-offs:** Results confirm that targeted link rewiring successfully degrades the global ranking sum of mastermind nodes, making them significantly harder to spotlight via standard automated pipelines.
* **Cascade Dynamics:** Simulations consistently demonstrate a drop in IC influence values and a rise in LT structural resistance across iterations. This confirms the theory that containing influence makes it harder to track the source.

---

## 🛠️ Tech Stack & Dependencies
* **Language:** Python
* **Core Libraries:** 
  * `networkx` for graph construction, network topologies, and centrality metrics.
  * `matplotlib` / `seaborn` for network and simulation plotting.
  * `numpy` / `pandas` for data manipulation and numerical modeling.

---

## Citation
* If you reference or build upon the concepts, analysis, or the C3R heuristic from this repository, please cite the dissertation report:
@mastersthesis{Sen2026Adversarial,
  author       = {Siddhartha Sen},
  title        = {Analysis of existing heuristics and implementing a new obfuscation method for hiding influential individuals in community networks},
  school       = {St. Xavier's College (Autonomous), Kolkata \& TCG CREST},
  year         = {2026},
  type         = {M.Sc. Dissertation}
}
