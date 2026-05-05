# Predictive-Quality-Control-of-Machined-Shafts

AI-powered bearing fault detection system using signal processing, machine learning, and deep learning. This project classifies 10 bearing fault conditions from vibration signals using Time Domain, Frequency Domain, and Wavelet Packet Transform (WPT) feature extraction with Random Forest and MLP models for predictive quality control.

---

## Overview

This project builds a complete AI-based predictive quality control pipeline for machined shafts by analyzing bearing vibration signals and detecting fault conditions automatically.

The system extracts features from multiple signal domains, evaluates their effectiveness, selects the best-performing feature domain, and applies machine learning and deep learning models for fault classification.

The objective is to identify bearing faults early before machine breakdown occurs.

**Real-world impact:**
Detects faults before machine failure, reduces downtime, lowers maintenance costs, and improves industrial safety.

---

## Problem Statement

Bearings are essential components in rotating machinery. Faults in bearings can cause:

* Machine breakdown
* Production loss
* Increased maintenance cost
* Worker safety risks

Traditional fault inspection methods are:

* Manual
* Slow
* Expensive
* Inconsistent

This project uses AI to automate fault detection using vibration signal analysis.

---

## Dataset

**Dataset Name:** CWRU Bearing Fault Dataset
**Source:** Case Western Reserve University
**Total Samples:** 4600
**Total Classes:** 10 Bearing Fault Conditions
**Sampling Rate:** 48,000 samples/second
**Data Format:** NPZ (`.npz`)
**Input Shape:** 32×32 per sample
**Signal Length per Sample:** 1024 values

The dataset consists of vibration signal samples collected under different bearing fault conditions and crack severity levels.

Each class contains **460 samples**, making the dataset balanced for classification.

### Class Distribution

| Class    | Description      | Crack Size | Samples |
| -------- | ---------------- | ---------: | ------: |
| Normal   | Healthy bearing  |       None |     460 |
| Ball_007 | Ball fault       | 0.007 inch |     460 |
| Ball_014 | Ball fault       | 0.014 inch |     460 |
| Ball_021 | Ball fault       | 0.021 inch |     460 |
| IR_007   | Inner Race fault | 0.007 inch |     460 |
| IR_014   | Inner Race fault | 0.014 inch |     460 |
| IR_021   | Inner Race fault | 0.021 inch |     460 |
| OR_007   | Outer Race fault | 0.007 inch |     460 |
| OR_014   | Outer Race fault | 0.014 inch |     460 |
| OR_021   | Outer Race fault | 0.021 inch |     460 |

### Dataset Quality

* Balanced dataset
* No missing values
* No duplicate samples
* Equal class representation

---

## Project Workflow

### 1. Data Loading

The dataset is loaded from an NPZ file containing:

* Raw vibration signal data
* Fault labels

---

### 2. Data Preprocessing

Preprocessing includes:

* Signal reshaping
* Label encoding
* Train-test splitting (80%-20%)

Purpose:

To prepare the dataset for feature extraction and modeling.

---

### 3. Feature Extraction

Three signal domains are used:

### Time Domain Analysis

Features extracted:

* Mean
* Standard Deviation
* RMS
* Kurtosis
* Skewness
* Peak Value
* Crest Factor

Purpose:

Captures statistical behavior of vibration signals.

---

### Frequency Domain Analysis

Extracted using FFT:

* Peak Frequency
* Mean Frequency
* Total Energy
* Low Band Energy
* Mid Band Energy
* High Band Energy
* Spectral Standard Deviation

Purpose:

Captures frequency-based fault patterns.

---

### Wavelet Packet Transform (WPT)

Extracted features:

* Energy coefficients
* Standard deviation

Purpose:

Captures localized time-frequency fault characteristics.

---

### 4. Feature Evaluation

Each feature domain is evaluated separately using Random Forest.

Feature domains compared:

* Time Domain
* Frequency Domain
* WPT Domain

The best performing feature set is selected automatically.

---

### 5. Machine Learning Model

## Random Forest

Used for:

* Feature comparison
* Baseline classification

Advantages:

* Fast training
* Strong baseline performance
* Robust classification

---

### 6. Deep Learning Model

## Multi-Layer Perceptron (MLP)

Used for:

* Advanced fault classification
* Nonlinear learning

Advantages:

* Better pattern recognition
* Improved predictive capability

---

### 7. Performance Evaluation

Metrics used:

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix

---

## Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* SciPy
* Scikit-learn
* TensorFlow
* PyWavelets
---

## Installation

Install required dependencies:

```bash
pip install numpy pandas matplotlib scipy scikit-learn pywavelets tensorflow
```

---

## How to Run

### Step 1: Install Dependencies

Run installation cells.

### Step 2: Upload Dataset

Upload the NPZ dataset file.

### Step 3: Run All Cells

Execute all notebook cells in sequence.

### Step 4: Analyze Results

Compare model performance and visualizations.

---

## Model Performance & Results

After extracting features from three different signal domains (Time Domain, Frequency Domain, and Wavelet Packet Transform), each feature set was evaluated separately using Random Forest to determine the most effective feature representation.

### Feature Domain Performance (Random Forest)

| Feature Domain   |   Accuracy |
| ---------------- | ---------: |
| Time Domain      | **88.70%** |
| Frequency Domain | **89.02%** |
| WPT Domain       | **93.26%** |

**Best Feature Domain:** Wavelet Packet Transform (WPT)


### Final Model Comparison

After selecting the best feature domain (WPT), two models were trained:

| Model                        |   Accuracy |
| ---------------------------- | ---------: |
| Random Forest                | **93.26%** |
| MLP (Multi-Layer Perceptron) | **92.72%** |

### Best Performing Model

**Best Overall Model:** Random Forest
**Best Accuracy Achieved:** **93.26%**


---

## Conclusion

This project presents an smart predictive quality control framework for bearing fault detection using signal processing and AI models.

By analyzing vibration signals and extracting meaningful features, the system can automatically classify fault conditions and improve industrial reliability, maintenance efficiency, and production safety.

---
