# Code and Implement

## Overview

This project investigates urban expansion detection from multi-temporal satellite imagery using Deep Learning and Explainable Artificial Intelligence (XAI).

Three models are evaluated:

* Custom CNN
* MobileNetV2 (Transfer Learning)
* ResNet50 (Transfer Learning)

Model explainability is performed using:

* Grad-CAM
* SHAP

---

## Dataset

### Dataset Name

SpaceNet 7 Multi-Temporal Urban Development

### Source

Kaggle

### Kaggle Dataset Path

```text
/kaggle/input/datasets/amerii/spacenet-7-multitemporal-urban-development
```

### Classification Task

Binary Classification:

| Class | Description        |
| ----- | ------------------ |
| 0     | No Urban Expansion |
| 1     | Urban Expansion    |

---

## Project Workflow

```text
SpaceNet 7 Dataset
        │
        ▼
Data Collection
        │
        ▼
Data Preprocessing
(Image Pair Selection, Difference Images)
        │
        ▼
Patch Extraction & Label Construction
        │
        ▼
Train / Validation / Test Split
        │
        ▼
Data Augmentation
        │
        ▼
 ┌───────────────────────────────┐
 │                               │
 ▼                               ▼
Custom CNN                 Transfer Learning
                            ├─ MobileNetV2
                            └─ ResNet50
 │                               │
 └───────────────┬───────────────┘
                 ▼
        Model Evaluation
                 │
                 ▼
       Explainable AI (XAI)
          ├─ Grad-CAM
          └─ SHAP
                 │
                 ▼
         Model Comparison
```

---

## Models

### 1. Custom CNN

Architecture:

```text
Input (224×224×3)
        │
Conv2D + ReLU
        │
Batch Normalization
        │
MaxPooling
        │
Conv2D + ReLU
        │
Batch Normalization
        │
MaxPooling
        │
Conv2D + ReLU
        │
Global Average Pooling
        │
Dense Layer
        │
Dropout
        │
Sigmoid Output
```

### 2. MobileNetV2

* ImageNet pretrained weights
* Transfer learning
* Frozen feature extractor
* Custom classification head

### 3. ResNet50

* ImageNet pretrained weights
* Residual learning architecture
* Transfer learning
* Custom classification head

---

## Evaluation Metrics

The following metrics are used to compare model performance:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix
* Classification Report
* Training Time
* Parameter Count

---

## Explainable AI

### Grad-CAM

Grad-CAM is used to visualize image regions contributing to model predictions.

Outputs:

* Correct prediction explanations
* Incorrect prediction explanations
* Heatmap overlays

### SHAP

SHAP is used to identify feature importance and explain model behavior.

Outputs:

* SHAP value plots
* Positive and negative feature contributions
* Sample-level explanations

---

## Repository Structure

```text
urban-expansion-detection-spacenet7/
│
├── README.md
├── notebooks/
│   └── spacenet7_urban_expansion_xai.ipynb
├── outputs/
│   ├── figures_pdf/
│   └── tables_csv/
```

---

## Output Files

### PDF Figures

* Dataset Samples
* Difference Image Examples
* Training Curves
* Confusion Matrices
* Grad-CAM Results
* SHAP Results
* Final Model Comparison Figures

### CSV Tables

* Dataset Description
* Class Distribution
* Classification Reports
* Confusion Matrices
* Model Performance Comparison

---

## How to Run

### Step 1: Open Kaggle Notebook

Upload or open:

```text
spacenet7_urban_expansion_xai.ipynb
```

### Step 2: Attach Dataset

Add the dataset:

```text
/kaggle/input/datasets/amerii/spacenet-7-multitemporal-urban-development
```

### Step 3: Run All Cells

Execute all notebook cells sequentially.

### Step 4: Review Outputs

Generated outputs will be saved automatically to:

```text
outputs/figures_pdf/
outputs/tables_csv/
```

---

## Technologies

### Programming Language

* Python 3.x

### Deep Learning Framework

* TensorFlow
* Keras

### Supporting Libraries

* NumPy
* Pandas
* Matplotlib
* Scikit-learn
* OpenCV
* SHAP

### Development Environment

* Kaggle Notebook

### Version Control

* GitHub

---

## Expected Outcomes

This project aims to:

* Detect urban expansion from multi-temporal satellite imagery.
* Compare Custom CNN, MobileNetV2, and ResNet50.
* Evaluate performance using multiple metrics.
* Interpret model decisions using Grad-CAM and SHAP.
* Produce publication-quality figures and tables.

---

## Author

**[Your Name]**

Machine Learning Course Project

---

## License

This project is intended for academic and educational purposes only.
