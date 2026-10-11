# Brain Tumor MRI Classifier

A deep learning project built using **PyTorch** and a custom Convolutional Neural Network (CNN) to classify brain MRI images into four categories: **Glioma, Meningioma, No Tumor, and Pituitary Tumor**, achieving **94.56% test accuracy**.

## Overview

- **Framework:** PyTorch
- **Model:** Custom CNN
- **Input Size:** 224 × 224 × 3
- **Dataset:** 7,200 MRI images
- **Classes:** 4
- **Test Accuracy:** 94.56%
- **Weighted F1-Score:** 0.94

## Dataset

The dataset contains four classes:
- Glioma
- Meningioma
- No Tumor
- Pituitary Tumor

It includes 5,600 training images and 1,600 testing images.

## Data Preprocessing

- Resizing images to 224 × 224 pixels
- Random flipping, rotation, and affine transformations
- Brightness and contrast adjustments
- Tensor conversion and ImageNet normalization

## Model Architecture

The CNN uses four convolutional layers with ReLU activation and max pooling, followed by fully connected layers and dropout for four-class classification.

## Training Configuration

| Parameter | Value |
|---|---|
| Optimizer | Adam |
| Learning Rate | `1e-4` |
| Loss Function | Cross Entropy Loss |
| Epochs | 80 |
| Batch Size | 32 |
| Dropout | 0.6 |
| Scheduler | ReduceLROnPlateau |

## Results

| Metric | Score |
|---|---:|
| Training Accuracy | 99.07% |
| Test Accuracy | **94.56%** |
| Weighted F1-Score | **0.94** |

Performance is evaluated using a classification report and confusion matrix.

## Project Structure

```text
brain-tumor-mri-classifier/
├── MRI-Brain-Tumor-Classifier.ipynb
├── README.md
├── requirements.txt
└── models/
    └── NeuroScan_AI_model.pth
```

## Installation

```bash
git clone <your-repository-url>
cd brain-tumor-mri-classifier
pip install -r requirements.txt
jupyter notebook MRI-Brain-Tumor-Classifier.ipynb
```

## Technologies Used

Python, PyTorch, Torchvision, NumPy, Matplotlib, Scikit-learn, and Jupyter Notebook.

## Disclaimer

This project is intended for educational and research purposes only. It is not clinically validated and should not be used as a substitute for professional medical diagnosis.
