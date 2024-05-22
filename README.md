# Offside and Foul Detection using VGG16


## Overview
This project aims to detect offside and foul instances in football videos. The classification is binary with two classes: 0 (offside) and 1 (foul). The project involves preprocessing and feature extraction from video frames and using the VGG16 model for classification.

## Dataset
- **Classes**: 2 (0 for offside, 1 for foul)
- **Data Preprocessing and Feature Extraction**:
  - **Frame Extraction and Preprocessing**: Extracts frames from video, resizes them to a target size, and saves the preprocessed frames for further processing.

## Model Structure
The VGG16 model is used as the base for feature extraction, and a custom classifier is added on top.

### VGG16 Model Structure
- **Base Model**: Pre-trained VGG16 model without the top classification layer, using weights from ImageNet.
- **Custom Layers**:
  - **Flatten Layer**: Flattens the input from the base model.
  - **Dense Layer**: 24 neurons with ReLU activation.
  - **Dropout Layer**: Dropout regularization with a rate of 0.5.
  - **Dense Layer**: 12 neurons with ReLU activation.
  - **Dropout Layer**: Dropout regularization with a rate of 0.5.
  - **Output Layer**: Single neuron with sigmoid activation for binary classification.

### Model Compilation
- **Optimizer**: Adam
- **Loss Function**: Binary cross-entropy
- **Metrics**: Accuracy

### Model Training
- **Batch Size**: 32
- **Epochs**: 10
- **Steps per Epoch**: Calculated based on the number of training frames.

## Model Performance Evaluation
The model's performance is evaluated using:
- **Accuracy**
- **Loss**
- **Precision**
- **Recall**
- **F1 Score**
- **Confusion Matrix**
