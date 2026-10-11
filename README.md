# Brain Tumor MRI Classification

A deep learning application developed using **PyTorch** and a custom Convolutional Neural Network (CNN) to classify brain MRI scans into four categories: **Glioma, Meningioma, No Tumor, and Pituitary Tumor**, achieving **94.56% test accuracy**.

## Project Overview

- **Framework:** PyTorch
- **Task:** Multi-Class Image Classification
- **Architecture:** Custom CNN
- **Input Resolution:** 224 × 224 × 3
- **Training Samples:** 5,600
- **Testing Samples:** 1,600
- **Classes:** 4
- **Test Accuracy:** 94.56%
- **Weighted F1-Score:** 0.94

## Model Architecture

The model consists of four convolutional layers for feature extraction, followed by fully connected layers for classification.

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
Class Prediction
```

## Dataset

The dataset comprises 7,200 brain MRI images distributed across four classes:

- **Glioma**
- **Meningioma**
- **No Tumor**
- **Pituitary Tumor**

The images are divided into 5,600 training samples and 1,600 testing samples.

## Data Preprocessing

Image preprocessing and augmentation techniques are applied to improve model generalization:

- Resize images to 224 × 224 pixels.
- Apply random horizontal flips and rotations.
- Perform random affine transformations.
- Adjust brightness and contrast.
- Convert images into tensors.
- Normalize images using ImageNet statistics.

## Training Configuration

| Parameter | Configuration |
|---|---|
| Optimizer | Adam |
| Learning Rate | `1e-4` |
| Weight Decay | `1e-4` |
| Loss Function | Cross Entropy Loss |
| Training Epochs | 80 |
| Batch Size | 32 |
| Learning Rate Scheduler | ReduceLROnPlateau |
| Dropout Rate | 0.6 |

## Performance Evaluation

| Metric | Result |
|---|---:|
| Training Accuracy | 99.07% |
| Test Accuracy | **94.56%** |
| Weighted F1-Score | **0.94** |

Model performance is assessed using a classification report and confusion matrix to analyze classification effectiveness and prediction errors.

## Prediction Example

```text
Predicted Class: Meningioma
Confidence Score: 99.99%
```

The confidence score reflects the model's estimated confidence in its prediction and does not represent clinical certainty.

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

## Installation and Execution

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd brain-tumor-mri-classifier
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Launch the Notebook

```bash
jupyter notebook MRI-Brain-Tumor-Classifier.ipynb
```

Run the notebook cells to perform data preprocessing, model training, performance evaluation, and MRI image classification.

## Technologies Used

- Python
- PyTorch
- Torchvision
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook

## Disclaimer

This project is intended solely for **educational and research purposes**. It has not been clinically validated and should not be used as a standalone diagnostic tool or as a substitute for professional medical evaluation.
