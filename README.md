# ECG Arrhythmia Classification using CNN–LSTM with Attention

## Overview

This project implements a deep learning framework for automated ECG arrhythmia classification using the MIT-BIH Arrhythmia Dataset.
The system combines convolutional neural networks (CNN) with LSTM layers to capture both spatial and temporal patterns in ECG signals.

The pipeline includes signal denoising, R-peak detection, heartbeat segmentation, class balancing using SMOTE, and deep learning classification.

## Key Features

* ECG signal denoising using Discrete Wavelet Transform (DWT)
* R-peak detection and heartbeat segmentation
* Handling class imbalance using SMOTE oversampling
* Hybrid CNN + LSTM architecture
* Channel attention mechanism for feature refinement
* Multi-class arrhythmia classification

## Dataset

MIT-BIH Arrhythmia Database

Source:
https://physionet.org/content/mitdb/

The dataset contains annotated ECG signals with multiple heartbeat types.

## Preprocessing Pipeline

1. Load ECG signals using WFDB
2. Apply wavelet denoising
3. Detect R-peaks from annotations
4. Segment individual heartbeats
5. Convert 15 classes → 5 arrhythmia categories
6. Balance dataset using SMOTE

## Model Architecture

Input (300 ECG samples)

→ Conv1D (16 filters)

→ Channel Attention

→ Max Pooling

→ Conv1D (32 filters)

→ Channel Attention

→ Max Pooling

→ Conv1D (64 filters)

→ Average Pooling

→ Conv1D (128 filters)

→ LSTM Layers

→ Fully Connected Layers

→ Softmax (5 Classes)

## Classes

| Label | Description      |
| ----- | ---------------- |
| N     | Normal           |
| S     | Supraventricular |
| V     | Ventricular      |
| F     | Fusion           |
| Q     | Unknown          |

## Training

Optimizer: Adam
Loss: Sparse Categorical Crossentropy
Epochs: 30
Batch Size: 128

## Results

The model achieves high performance on ECG arrhythmia classification.

Metrics include:

* Training Accuracy
* Test Accuracy
* Per-class sensitivity
* Specificity
* F1-score

Confusion matrix and class-wise metrics are computed after training.

## Repository Structure

```
ecg-arrhythmia-classification/

README.md
requirements.txt

notebooks/
    ecg_arrhythmia_model.ipynb

results/
    confusion_matrix.png
    class_balancing.png
    denoised_segmented_ecg.png
```

## Installation

Clone the repository

```
git clone https://github.com/yourusername/ecg-arrhythmia-classification.git
cd ecg-arrhythmia-classification
```

Install dependencies

```
pip install -r requirements.txt
```

Run the notebook

```
jupyter notebook notebooks/ecg_arrhythmia_model.ipynb
```

## Author

Mohit Anand
B.Tech Computer Science
VIT Chennai
