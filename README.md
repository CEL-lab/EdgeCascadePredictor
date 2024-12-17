# EdgeCascadePredictor

## Overview

EdgeCascadePredictor is a repository for edge-level prediction of cascading failures in power grids. By leveraging Graph Neural Networks (GNNs), this project identifies vulnerable edges in a power grid to improve predictive accuracy and provide actionable insights. The dataset is adapted to focus on edge-level tasks, with experiments comparing baseline features and advanced edge features (like edge betweenness centrality).

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

---

## Dataset

The dataset used in this repository is adapted from the PowerGraph dataset. It has been modified to include edge-level labels and features for predicting edge failures across power grid states.

### **Dataset Files**:
- **`edge_dataset_baseline.pt`**: Contains baseline features (original node and edge features).
- **`edge_dataset_advanced.pt`**: Contains advanced features (edge betweenness centrality added to baseline features).

---

## Code

### **1. Dataset Adaptation (`1_dataset_adaptation.ipynb`)**
This Jupyter Notebook adapts the original PowerGraph dataset to edge-level tasks:
- **Edge Labels**: Created by comparing edges across consecutive states.
  - `Label 0`: Edge remains active.
  - `Label 1`: Edge fails (disconnected in the next state).
- The processed datasets are saved in `.pt` format.

### **2. Baseline Experiment (`2_baseline_experiment.ipynb`)**
This notebook implements a GNN-based model to predict edge-level failures using the baseline dataset:
- **Features**: Original node and edge attributes (e.g., power flow, line ratings).
- **Model**: GraphSAGE-based GNN.
- **Output**: Performance metrics including accuracy, precision, recall, and F1-score.

### **3. Advanced Feature Experiment (`3_advanced_experiment.ipynb`)**
This notebook extends the baseline experiment by incorporating **edge betweenness centrality** as an additional edge feature:
- **Features**: Baseline features + edge betweenness centrality.
- **Model**: GraphSAGE-based GNN.
- **Comparison**: Evaluates performance improvement over the baseline experiment.

---

## How to Use

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/EdgeCascadePredictor.git
   cd EdgeCascadePredictor
