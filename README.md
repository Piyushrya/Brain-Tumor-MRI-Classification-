
# Brain Tumor MRI Classifier

A deep learning project built with **PyTorch** and a custom Convolutional Neural Network (CNN) to classify brain MRI images into four categories: **Glioma, Meningioma, No Tumor, and Pituitary Tumor**.

The model achieves **94.56% test accuracy** and supports image classification with confidence-based predictions.

## Overview

- **Framework:** PyTorch
- **Task:** Multi-Class Image Classification
- **Model:** Custom CNN
- **Input Size:** 224 × 224 × 3
- **Training Images:** 5,600
- **Testing Images:** 1,600
- **Number of Classes:** 4
- **Test Accuracy:** 94.56%
- **Weighted F1-Score:** 0.94

## Model Architecture

```text
Input Image (224 × 224 × 3)
          |
          v
Conv2D (3 → 32) + ReLU + MaxPool
          |
          v
Conv2D (32 → 64) + ReLU + MaxPool
          |
          v
Conv2D (64 → 128) + ReLU + MaxPool
          |
          v
Conv2D (128 → 256) + ReLU + MaxPool
          |
          v
Flatten
          |
          v
Linear (50176 → 256) + ReLU
          |
          v
Dropout (0.6)
          |
          v
Linear (256 → 4)
          |
          v
Predicted Class
```

## Dataset

The dataset contains four categories of brain MRI images:

- Glioma
- Meningioma
- No Tumor
- Pituitary Tumor

## Data Preprocessing

The following transformations are applied during preprocessing:

- Resize images to 224 × 224 pixels.
- Random horizontal flipping.
- Random rotation.
- Random affine transformations.
- Brightness and contrast adjustment.
- Convert images to tensors.
- Normalize using ImageNet mean and standard deviation.

## Training Configuration

| Parameter | Value |
|---|---|
| Optimizer | Adam |
| Learning Rate | `1e-4` |
| Weight Decay | `1e-4` |
| Loss Function | Cross Entropy Loss |
| Epochs | 80 |
| Batch Size | 32 |
| Scheduler | ReduceLROnPlateau |
| Dropout | 0.6 |

## Results

| Metric | Score |
|---|---:|
| Training Accuracy | 99.07% |
| Test Accuracy | **94.56%** |
| Weighted F1-Score | **0.94** |

The model is evaluated using a classification report and confusion matrix.

## Prediction Example

```text
Prediction: Meningioma
Confidence: 99.99%
```

The confidence score represents the model's estimated confidence in its prediction and should not be interpreted as clinical certainty.

## Project Structure

```text
brain-tumor-mri-classifier/
│
├── MRI-Brain-Tumor-Classifier.ipynb
├── README.md
├── requirements.txt
└── models/
    └── NeuroScan_AI_model.pth
```

## Installation

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd brain-tumor-mri-classifier
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the notebook

```bash
jupyter notebook MRI-Brain-Tumor-Classifier.ipynb
```

Execute the notebook cells to explore preprocessing, model training, evaluation, and predictions.

## Technologies Used

- Python
- PyTorch
- Torchvision
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook


## Disclaimer

This project is intended for **educational and research purposes only**. It is not a clinically validated diagnostic system and must not replace professional medical evaluation.
