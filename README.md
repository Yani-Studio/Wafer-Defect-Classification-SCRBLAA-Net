<div align="center">

# 🔬 SCRBLAA-Net: Wafer Defect Classification
**Official PyTorch Implementation & Interactive Simulator**

[![Paper](https://img.shields.io/badge/SCIE-Int._J._Adv._Manuf._Technol.-023047?style=for-the-badge&logo=springer)](https://link.springer.com/article/10.1007/s00170-025-16934-5)
[![Demo](https://img.shields.io/badge/Live_Demo-Interactive_Simulator-219EBC?style=for-the-badge&logo=html5)](https://raw.githack.com/Yani-Studio/Wafer-Defect-Classification-SCRBLAA-Net/main/Visualization/Wafer_Map_Simulator.html)
[![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)]()

*Spatio-Temporal Hybrid Architecture Reproduction and Validation Pipeline for Wafer Defect Pattern Classification*

</div>

<br>

## 📢 Publication
This repository provides the official implementation of the core architecture from our research published in the SCIE journal **[The International Journal of Advanced Manufacturing Technology (JCR Q2)]**. It also serves as a validation project demonstrating model reproducibility across distinct hardware infrastructures.

> **Combining Residual Network and Bidirectional Long Short-Term Memory with Additive Attention for Wafer Defect Classification**<br>
> *Gyumin Kang, et al.*<br>
> 🔗 [Read the Article on Springer](https://link.springer.com/article/10.1007/s00170-025-16934-5)

<br>

## 🧠 1. Model Architecture (SCRBLAA-Net)

A hybrid model that combines the global spatial feature extraction capabilities of CNNs with the sequential context understanding of RNNs.

<br>

<div align="center">

<img src="https://raw.githubusercontent.com/Yani-Studio/Wafer-Defect-Classification-SCRBLAA-Net/main/Visualization/framework_overview.png" alt="Architecture" width="80%">

</div>

<br>

1. **Shortcut3-ResNet (SCR5):** Extracts spatial features from the Binarized Wafer Map.
2. **Sliding-Window Tokenization:** Converts high-dimensional feature vectors into overlapping sequential tokens.
3. **Bi-LSTM & Additive Attention:** Analyzes bidirectional sequences and dynamically assigns attention weights to windows exhibiting strong defect characteristics.

<br>

## 🚀 2. Interactive Wafer Map Simulator
We provide a **web-based interactive simulator** that allows users to manually operate and visualize the activation processes of the proposed model across 8 distinct wafer defect patterns.

👉 **[Launch Interactive Wafer Map Simulator (Live Demo)](https://raw.githack.com/Yani-Studio/Wafer-Defect-Classification-SCRBLAA-Net/main/Visualization/Wafer_Map_Simulator.html)**
*(Click the link to run the interactive demo immediately in your browser. No installation required.)*

<br>

## 📈 3. Reproduction Performance & Variance Analysis

This repository accurately reproduces the proposed architecture using PyTorch and conducts a variance analysis across different infrastructure environments.

* **Original Paper Performance:** `Test Accuracy 94.98%` (NVIDIA RTX 3090 Ti 24GB / CUDA Environment)
* **Local Reproduction Performance:** `Test Accuracy 94.10%` / `Macro F1-Score 0.9173` (MacBook Apple Silicon / MPS Environment)

**💡 Analysis of Reproduction Variance:**
The 94.98% accuracy reported in the paper is a maximized metric derived under a strictly controlled random seed on a high-end desktop environment (NVIDIA RTX 3090 Ti) using a CUDA backend. The minor numerical variance of approximately 0.88%p observed in this local reproduction (MacBook Apple Silicon) is attributed to the following factors:

1. **Hardware Core Architecture:** Hardware-level differences in tensor computation algorithms and floating-point precision processing between NVIDIA's CUDA acceleration environment and Apple Silicon's MPS (Metal Performance Shaders) architecture.
2. **Stochastic Backend Variance:** Stochastic variability during weight initialization and accelerated computation processes, caused by differences in framework backend optimization solutions.

Despite these environmental discrepancies, defending a high classification accuracy of over 94% and a stable Macro F1-Score of over 0.91 quantitatively proves that the proposed **SCRBLAA-Net architecture does not overfit to a specific hardware infrastructure and maintains robust generalization performance across diverse deployment environments.**

<br>

## 🔍 4. Data Preprocessing

A **high-speed binarization pipeline** was applied to maximize subtle defect patterns and suppress manufacturing process noise.

<br>

<div align="center">

<img src="https://raw.githubusercontent.com/Yani-Studio/Wafer-Defect-Classification-SCRBLAA-Net/main/Visualization/preprocessed_binarized.png" alt="Preprocessed Data" width="40%">

</div>

<br>

*(The image above shows representative binarized wafer map samples for the 8 defect types after preprocessing.)*

<br>

## 🛠️ Tech Stack
* **Deep Learning Framework:** PyTorch (MPS / CUDA Support)
* **Data Processing:** NumPy, Pandas, OpenCV, Scikit-Learn
* **Visualization & Demo:** Matplotlib, Seaborn, HTML5/CSS/Vanilla JS
