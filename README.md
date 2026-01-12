# Fraud Detection using Graph Neural Networks (GNN)

## Overview
This project implements **fraud detection using Graph Neural Networks (GNNs)** by modeling transactional data as a **graph-based learning problem**. Instead of relying solely on tabular features, the approach captures **relational dependencies** between entities such as transactions, accounts, or clients, enabling more expressive fraud pattern learning.

A **HinSAGE (Heterogeneous GraphSAGE)** architecture is used to perform **binary fraud classification**, leveraging neighborhood aggregation to enhance predictive performance on imbalanced fraud datasets.

---

## Key Concepts
- Graph Neural Networks (GNN)
- Heterogeneous Graph Modeling
- HinSAGE / GraphSAGE
- Inductive Node Embeddings
- Fraud Detection
- Imbalanced Classification
- Neighborhood Aggregation
- PyTorch Deep Learning

---

## Methodology

### 1️⃣ Graph Construction
- Transactional data is transformed into a **graph structure**.
- Nodes represent entities (e.g., transactions or related actors).
- Edges encode relationships between entities.
- Graphs are constructed using **NetworkX**.

### 2️⃣ Feature Engineering
- Node features are derived from transaction attributes.
- Features are propagated across neighbors to capture contextual signals.

### 3️⃣ Model Architecture
- A **HinSAGE-based GNN** is implemented.
- The model learns **inductive embeddings**, allowing generalization to unseen nodes.
- Implemented and trained using **PyTorch**.

### 4️⃣ Training & Evaluation
- Binary classification objective (fraud vs non-fraud).
- **Binary Cross-Entropy Loss** optimized during training.
- Handled **class imbalance**, common in fraud datasets.
- Train–test split used for performance evaluation.

---

## 🧩 Model Architecture (Pseudo-Diagram)

```text
Transaction Graph
(Nodes + Edges)
│
▼
+-------------------+
| Node Features |
| (Transaction Data)|
+-------------------+
│
▼
+-------------------+
| HinSAGE Layer 1 |
| Neighbor Sampling |
| + Aggregation |
+-------------------+
│
▼
+-------------------+
| HinSAGE Layer 2 |
| Higher-order |
| Neighborhood Info |
+-------------------+
│
▼
+-------------------+
| Node Embeddings |
| (Graph Context) |
+-------------------+
│
▼
+-------------------+
| Fully Connected |
| Classification |
+-------------------+
│
▼
Fraud Probability
(Binary Prediction)
```
