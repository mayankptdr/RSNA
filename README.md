# 🦴 RSNA Knee Abnormality Detection

<div align="center">

### Multi-Label Knee MRI Abnormality Classification using DINOv2 Vision Transformers

[![Python](https://img.shields.io/badge/Python-3.11-blue)]()
[![PyTorch](https://img.shields.io/badge/PyTorch-DeepLearning-red)]()
[![DINOv2](https://img.shields.io/badge/Backbone-DINOv2-green)]()
[![Kaggle](https://img.shields.io/badge/Kaggle-RSNA-orange)]()

### 🏆 Public Leaderboard AUROC: **0.823**

Built from scratch using weak supervision, DICOM processing, Vision Transformers, and large-scale MRI data engineering.

</div>

---

## 🎯 Project Overview

This project was developed for the **RSNA Knee Abnormality Detection Challenge**, where the objective is to identify multiple abnormalities from knee MRI scans.

The challenge contains:

- 📦 4,407 MRI studies
- 🩻 Multi-sequence DICOM scans
- 🧠 12 abnormality classes
- 📋 Only 58 expert-labeled studies
- 🌍 Multilingual radiology reports

To overcome the severe lack of labels, a weak-supervision pipeline was built using **Google Gemini** to convert radiology reports into structured training labels.

---

## 🚀 Key Highlights

✅ Processed **600GB+ MRI Data**

✅ Built Multilingual Weak Label Pipeline using Gemini

✅ DICOM-Based MRI Processing Pipeline

✅ DINOv2 Vision Transformer Training

✅ Slice-Level Attention Pooling

✅ Slot-Level Attention Pooling

✅ Full Checkpoint Recovery System

✅ 5 Fold Cross Validation

✅ Public Leaderboard AUROC **0.823**

---

## 🎥 Demo Video

The repository contains a demonstration video:

```text
assets/demo/slices.mp4
```

Download and view the demo locally for the complete MRI slice visualization.

---

## 🏗️ Pipeline Architecture

```text
DICOM MRI Study
       │
       ▼
Series Selection
       │
       ▼
MRI Normalization
       │
       ▼
Physical-Space Cropping
       │
       ▼
Representative Slice Extraction
       │
       ▼
DINOv2 Backbone
       │
       ▼
Slice Attention Pooling
       │
       ▼
Slot Attention Pooling
       │
       ▼
Multi-Label Classification Head
       │
       ▼
12 Knee Abnormalities
```

---

## 📊 Results

| Model | CV AUROC | Public Leaderboard |
|---------|---------|---------|
| 3D ResNet18 | 0.7304 | - |
| DINOv2 V1 | 0.7875 | **0.823** |
| DINOv2 V2 | 0.7811 | Pending |

---

## 🧠 Weak Label Generation

A Gemini-powered weak supervision framework was developed to convert free-text radiology reports into structured labels.

### Workflow

```text
Radiology Report
        │
        ▼
Google Gemini
        │
        ▼
Structured Findings
        │
        ▼
Training Labels
        │
        ▼
DINOv2 Training
```

### Label Format

```python
1     = Positive Finding
0     = Negative Finding
None  = Not Mentioned
```

---

## 🩻 Data Engineering

### Challenges

- 600GB+ raw MRI dataset
- DICOM-based imaging workflow
- Kaggle storage limitations
- Limited GPU availability

### Solutions

- Parallel preprocessing notebooks
- DICOM metadata driven sorting
- MRI intensity normalization
- Physical-space cropping
- Float16 cache optimization
- Distributed cache generation

---

## 🤖 Model Development

### V1 — 3D CNN Baseline

- Multi-Branch ResNet18
- 3D MRI Processing
- Cross Validation

### V2 — DINOv2

- DINOv2-S/14 Backbone
- Attention Pooling
- Multi-Plane MRI Processing

### V3 — Enhanced DINOv2

- RGB Slice Grouping
- Physical Slice Ordering
- Masked Supervision
- Improved Weak Labels

---

## 🛠️ Tech Stack

### Deep Learning

- PyTorch
- Torchvision
- DINOv2

### Medical Imaging

- pydicom
- OpenCV

### Machine Learning

- Scikit-Learn
- Iterative Stratification

### LLM

- Google Gemini API

### Infrastructure

- Kaggle Notebooks
- Google Colab

---

## 📂 Repository Structure

```text
RSNA
│
├── assets
│   └── demo
│       └── slices.mp4
│
├── notebooks
│   ├── 3d_cnn_baseline
│   ├── cache_builders
│   ├── data_pipeline
│   ├── dinov2_v1
│   ├── dinov2_v2
│   └── inference
│
└── README.md
```

---

## 🔮 Future Work

- Expert Verified Labels
- Test Time Augmentation
- Model Ensembling
- Additional Vision Transformers
- Larger Training Schedules

---

## 👨‍💻 Author

### Mayank Patidar

B.Tech AI & Data Science  
AI Engineer | Computer Vision | Deep Learning

🔗 GitHub: https://github.com/mayankptdr

---

⭐ If you found this project useful, consider starring the repository.
