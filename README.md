# BIDGNN: BioGPT-Enhanced Dual-Graph Framework for DDI Extraction

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.9-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-1.12.0-orange.svg)](https://pytorch.org/)

This repository contains the official implementation and data for the paper:  
**"Unveiling Rare Drug Interactions: A BioGPT-Enhanced Dual-Graph Framework for Robust Pharmacovigilance"**

> **Abstract:** > BIDGNN represents a unified framework that synergizes generative intelligence with structural reasoning. It employs a **BioGPT-driven GAN** to synthesize realistic training samples for rare classes (resolving data scarcity) and a **Dual-Graph Neural Network (DGNN)** to capture both explicit syntactic and implicit semantic dependencies (resolving semantic complexity).

---


## 📂 Project Structure

| File / Directory | Description |
| :--- | :--- |
| `maincode_DGNN.py` | **Core Script**: Handles data loading, graph construction, training, and evaluation. |
| `data_augmentation.py` | **BioGPT-GAN Module**: Used to generate synthetic samples for rare classes (*Advice*, *Int*). |
| `data/` | (Optional) Folder containing dataset files (`train.tsv`, `dev.tsv`, `test.tsv`). |
| `augmented_train_data.tsv` | The pre-generated augmented training dataset. |
| `README.md` | This document. |

---

## 🛠️ Requirements

The code has been tested with **Python 3.9** and **PyTorch 1.12.0**. 

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/Hero-Legend/BIDGNN.git](https://github.com/Hero-Legend/BIDGNN.git)
   cd BIDGNN
2. **Install dependencies:**
   ```bash
   pip install torch==1.12.0 torchvision==0.13.0 torchaudio==0.12.0
   pip install transformers numpy pandas scikit-learn tqdm

---

## 🚀 How to Run
1. **Data Augmentation (Offline)**
   Our framework uses an offline augmentation strategy to handle class imbalance. If you wish to regenerate the synthetic data:
   ```bash
   python data_augmentation.py
   Output: augmented_train_data.tsv
2. **Training and Evaluation**
   To train the BIDGNN model and evaluate it on the DDI 2013 test set:
   ```bash
   python maincode_DGNN.py

---

## 📊 Performance
BIDGNN achieves state-of-the-art performance on the DDI Extraction 2013 benchmark:
|`Metric`|Score (%)|
|`Precision`|82.55|
|`Recall`|84.62|
|`F1-Score`|83.57|

---

## 📜 License
This project is licensed under the MIT License - see the LICENSE file for details.

---

## 👏 Acknowledgments
This work is supported by National Natural Science Foundation of China
under Grant No.82160591, Key Project of Clinical Research of Shanghai East Hospital, Tongji University under Grant No.DFLC-2022012, Key Specialty Construction Project of Shanghai Pudong New Area Health Commission under Grant No.PWZzk2022-02, Outstanding Leaders Training Program of Pudong Health Bureau of Shanghai under Grant No.PWR12023-02, Shanghai Science Technology Innovation Action Plan under Grant No.23Y11909000, Science Research Project of Hebei Education Department
under Grant No.QN2025011, Doctoral Research Start-up Fund Program of The National Police University for Criminal Justice under Grant No.BSQDW202150 and University-level Research Project of The National Police University for Criminal Justice under Grant No.XYY202501.



