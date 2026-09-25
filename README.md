# Q-FloodFusion-RS

### Quantum-Adaptive Multimodal Deep Learning for Flood Boundary Segmentation

Q-FloodFusion is a **hybrid quantum-classical multimodal deep learning framework** for flood segmentation from heterogeneous remote-sensing data. The model combines **Sentinel-1 SAR, Sentinel-2 multispectral imagery, DEM, and precipitation information** and uses a compact **4-qubit variational quantum circuit** for adaptive feature modulation.

### Dataset

**SEN1FLOODS11 – 8 Channel Remote Sensing Dataset**

[Kaggle Dataset](https://www.kaggle.com/datasets/oindrieelmondal/sen1floods11-8-channel-remote-sensing-dataset)

**8 Input Channels:**

* Sentinel-1 VV
* Sentinel-1 VH
* Sentinel-2 Green
* Sentinel-2 Red
* Sentinel-2 NIR
* Sentinel-2 SWIR
* DEM
* 7-day cumulative precipitation

Input size: **512 × 512 × 8**

### Architecture

```text
8-Channel Input
      ↓
Dual-Branch Residual Encoders
      ↓
CBAM Attention
      ↓
Cross-Modal Fusion
      ↓
Multi-Scale Dilated Context
      ↓
4-Qubit Variational Quantum Circuit
      ↓
Adaptive Feature Modulation
      ↓
Attention-Gated Decoder
      ↓
Flood Segmentation Mask
```

### Quantum Module

The quantum component uses:

* 4 qubits
* RX, RY and RZ rotations
* 2 variational layers
* Ring CNOT entanglement
* Pauli-Z expectation measurements

The quantum circuit generates a compact adaptive feature representation for reweighting the fused multimodal features.

### Training

| Parameter          | Value            |
| ------------------ | ---------------- |
| Samples            | 446              |
| Train / Val / Test | 312 / 67 / 67    |
| Epochs             | 100              |
| Batch Size         | 4                |
| Optimizer          | AdamW            |
| Learning Rate      | 3 × 10⁻⁴         |
| Scheduler          | Cosine Annealing |
| Seed               | 42               |
| Qubits             | 4                |

### Evaluation

The model is evaluated using:

**Accuracy, Precision, Recall, F1/Dice, and IoU.**

Reported performance includes approximately **0.60–0.62 validation IoU**, **0.74–0.75 validation Dice/F1**, and **96.59% reported pixel accuracy**.

### Key Features

* Multimodal remote-sensing fusion
* SAR
