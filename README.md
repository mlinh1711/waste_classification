# Multi-class Waste Classification using CNN

This repository contains the implementation and experimental analysis of a deep learning project on **multi-class waste image classification** using Convolutional Neural Networks (CNNs).  
The project was developed as a major assignment for the *Deep Learning* course at the National Economics University.

The main objective is to automatically classify waste images into four categories — **Metal, Plastic, Paper, and Miscellaneous** — to support intelligent waste sorting and recycling systems.

---

## Project Overview

Manual waste sorting is time-consuming, error-prone, and inefficient at scale. This project explores how deep learning, particularly CNN-based image classification, can be used to automate waste classification with high accuracy.

Three model approaches are implemented and compared:

- A **Custom CNN** designed from scratch
- **ResNet50** using transfer learning
- **DenseNet121** using transfer learning

All models are evaluated on the same dataset using consistent metrics to ensure fair comparison.

---

## Dataset

- **Dataset name:** Multiclass Waste Classification Dataset  
- **Source:** Kaggle  
- **Total images:** 16,281  
- **Classes:**
  - Metal
  - Plastic
  - Paper
  - Miscellaneous

### Dataset Split
- Training: 13,024 images (80%)
- Validation: 1,628 images (10%)
- Test: 1,629 images (10%)

The dataset exhibits class imbalance, with Plastic being the most dominant class and Metal the smallest. Data augmentation and class-aware training strategies were applied to mitigate this issue.

All images were resized to **224 × 224** and normalized before training.

---

### File Descriptions

- **EDA waste classification.ipynb**  
  Exploratory data analysis including class distribution, image dimensions, color statistics, and data integrity checks.

- **Custom CNN.ipynb**  
  Implementation of a CNN built from scratch using convolutional blocks, batch normalization, dropout, and global average pooling.

- **DenseNet121_model.ipynb**  
  Transfer learning approach using DenseNet121 pretrained on ImageNet, with a two-phase training strategy (feature extraction + fine-tuning).

- **RESNET_50.ipynb**  
  Transfer learning approach using ResNet50 with residual connections and selective fine-tuning of top layers.

---

## Model Architectures

### Custom CNN
- Seven convolutional blocks with increasing filter depth
- Batch Normalization and ReLU activation
- Global Average Pooling instead of Flatten
- Dropout for regularization
- Optimizer: Adam with cosine decay learning rate
- Loss: Categorical Crossentropy with label smoothing

### DenseNet121
- Pretrained on ImageNet
- Dense connectivity for efficient feature reuse
- Two-stage training: frozen backbone followed by partial fine-tuning
- Dropout and class weighting applied

### ResNet50
- Pretrained on ImageNet
- Residual learning to mitigate vanishing gradients
- Fine-tuning of upper convolutional layers
- Extensive data augmentation and regularization

---

## Experimental Results

| Model        | Accuracy | Precision | Recall | F1-score |
|-------------|----------|-----------|--------|----------|
| Custom CNN  | 0.87     | 0.87      | 0.87   | 0.87     |
| DenseNet121| 0.95     | 0.95      | 0.95   | 0.95     |
| ResNet50   | 0.98     | 0.98      | 0.98   | 0.98     |

ResNet50 achieved the best overall performance, demonstrating the effectiveness of deep residual networks and transfer learning for this task.

---

## Conclusion

The results confirm that CNN-based models can effectively learn discriminative visual features for waste classification. While the custom CNN provides a solid baseline, pretrained architectures — especially ResNet50 — significantly improve accuracy and generalization.

This study highlights the potential of deep learning in building intelligent waste management systems that can reduce manual labor, improve recycling efficiency, and support environmental sustainability.

---

## Authors

- Pham Ngoc Nhi  
- Vu Mai Linh  
- Nguyen Hoang Nghia  
- Nguyen Thanh Tung  

Course: Deep Learning  
Instructor: Dr. Nguyen Thi Kim Ngan  
National Economics University, Hanoi (2025)

---

## References

LeCun et al. (1998), Goodfellow et al. (2016), Krizhevsky et al. (2012),  
Taye (2023), and other foundational works on CNNs and deep learning.


