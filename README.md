# HistoMetPath-Deep-Learning-for-Breast-Cancer-Histology-Metastasis-Analysis
HistoMetPath combines advanced deep learning with histopathology to accurately distinguish primary from metastatic breast cancer. Our framework integrates multi-modal tissue analysis to enhance diagnostic precision, predict metastatic potential, and support personalized treatment planning for improved patient outcomes.

# Breast Cancer Pathology Analysis

This project is a multi-modal deep learning framework for breast cancer pathology analysis. It integrates histopathology images, whole slide images (WSI), immunofluorescence, pathology details, genomic data, and clinical data to perform:

- Tumor classification (Normal, DCIS, IDC, ILC, Mixed, Other)
- Metastatic classification (primary vs. metastatic)
- Survival prediction

## Components

### Configuration
- Defines data paths, model architecture, training hyperparameters, and cross-validation settings.

### Multi-Modal Network
- Uses Vision Transformers (ViT) for each image modality.
- Aggregates multiple patches per slide.
- Fuses image features with genomic and clinical features using cross-attention.
- Includes task-specific heads for classification and survival analysis.

### Training Pipeline
- Loads configuration and data.
- Applies transformations and augmentations.
- Implements K-fold cross-validation.
- Trains using PyTorch Lightning.

### Custom Transforms
- Image preprocessing and augmentation tailored for pathology data.

### Dataset Class
- Loads multi-modal image, clinical, and genomic data.
- Supports survival and metastatic labels.

### Training Loop
- Computes losses and tracks metrics.
- Uses Cosine Annealing LR scheduler.

### Vision Transformer
- Custom ViT architecture for pathology images.
- Outputs class token and patch-level embeddings.

### Visualization Utilities
- Visualizes predictions and attention maps.
- Generates patient-level reports.

## Scientific Relevance
- Supports precision oncology and digital pathology.
- Enables robust decision-making through multi-modal data integration.

## Usage
1. Configure paths and parameters in `Breast Cancer Pathology Configuration.py`
2. Train the model using `Main Training Script.py`
3. Visualize results with `Visualization Utilities for Pathology Results.py`

## Output
- Tumor classification accuracy
- Metastatic AUC
- Survival C-index
- Patient-level visual reports
