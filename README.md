# EdgeCascadePredictor

## Overview

EdgeCascadePredictor is a repository for edge-level prediction of cascading failures in power grids. By leveraging Graph Neural Networks (GNNs), this project identifies vulnerable edges in a power grid to improve predictive accuracy and provide actionable insights. The dataset is adapted to focus on edge-level tasks, with experiments comparing baseline features and advanced edge features (like edge betweenness centrality).

---

## Repository Structure

The repository is organized as follows:
```
EdgeCascadePredictor/
│
├── Data/
│   ├── edge_dataset_baseline.pt       # Dataset with baseline node and edge features
│   ├── edge_dataset_advanced.pt       # Dataset with edge betweenness centrality (advanced features)
│
├── Code/
│   ├── 1_dataset_adaptation.ipynb     # Script to adapt PowerGraph dataset to edge-level tasks (label creation)
│   ├── 2_baseline_experiment.ipynb    # Baseline GNN experiment with original features
│   ├── 3_advanced_experiment.ipynb    # Experiment using advanced features (edge betweenness centrality)
│
└── README.md                          # Project documentation (this file)
```
