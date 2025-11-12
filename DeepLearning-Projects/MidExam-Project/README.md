# **Custom CNN vs. ResNet-18: A Comparative Study on CIFAR-10**

## 📝 **Project Overview**
This project documents the process of building, training, and evaluating two distinct Convolutional Neural Network (CNN) architectures for image classification, using the CIFAR-10 dataset as a benchmark. The first model is a custom-built CNN, while the second is a ResNet-18 architecture modified for this specific dataset. The performance of both models is compared using accuracy, precision, recall, and F1-score.

## 🔍 **Background**
Image classification remains a fundamental task in computer vision and deep learning. The CIFAR-10 dataset is a standard benchmark for this purpose, consisting of 60,000 32x32 color images across 10 distinct classes (e.g., 'airplane', 'automobile', 'bird', 'cat'). The dataset is partitioned into 50,000 images for training and 10,000 for testing.

This project was undertaken to fulfill the requirements of the Deep Learning midterm exam.

## 🎯 **Project Goals**
1.  **Classification:** To successfully classify the CIFAR-10 dataset using both a custom CNN and an adapted, pre-trained ResNet-18 model from PyTorch.
2.  **Optimization:** To conduct hyperparameter tuning for the custom CNN to identify the optimal parameters that maximize accuracy, precision, and recall.
3.  **Comparison:** To benchmark the optimized custom CNN against the modified ResNet-18 model, determining which architecture provides superior performance on the CIFAR-10 dataset.

## ⚙️ **Methodology & Configuration**
1.  **Data Preparation**
    * **Dataset:** CIFAR-10 (50,000 training, 10,000 test images).
    * **Data Partition:** The 50,000 training images were split into a 90% training set (45,000) and a 10% validation set (5,000).
    * **Augmentation & Transforms:**
        * *Training Set:* `RandomCrop(32, padding=4)`, `RandomHorizontalFlip()`, `Normalize(mean=[0.5,0.5,0.5], std=[0.5,0.5,0.5])`.
        * *Validation & Test Sets:* `Normalize(mean=[0.5,0.5,0.5], std=[0.5,0.5,0.5])`.

2.  **Model Architectures**
    * **Model 1: Custom CNN**
        * *Architecture:* This model consists of three convolutional blocks. Each block includes `Conv2d`, `BatchNorm2d`, and `ReLU`, followed by a `Pooling` layer (Max or Avg). Extracted features are then flattened and passed through two Fully Connected (`Linear`) layers, incorporating `Dropout` for final classification.
        * *Tuned Hyperparameters:* The optimal configuration found after hyperparameter search was:
            * Conv. Filters: (128, 256, 512)
            * FC Neurons: 512
            * Dropout Rate: 0.5
            * Batch Size: 64
            * Optimizer: SGD (momentum=0.9)
            * Learning Rate: 0.01
            * Weight Decay: 5e-4
    * **Model 2: Modified ResNet-18**
        * *Architecture:* Utilized the ResNet-18 architecture from `torchvision.models`, modified for CIFAR-10. The initial `conv1` layer was changed to a 3x3 kernel with stride 1, the initial `maxpool` was replaced with `nn.Identity()`, and the final `fc` layer was replaced to produce 10 outputs.
        * *Training Settings:*
            * Epochs: 60
            * Optimizer: SGD
            * Learning Rate: 0.1
            * Momentum: 0.9
            * Weight Decay: 5e-4
            * Scheduler: `CosineAnnealingLR`
            * Early Stopping: Patience = 15

## 🧮 **Performance Results**
| Metric | Custom CNN (Best) | Modified ResNet-18 |
| :--- | :---: | :---: |
| Training Accuracy | 93.10% | 99.92% |
| Validation Accuracy | 89.46% | 94.52% |
| **Test Accuracy** | **89.26%** | **94.25%** |
| F1-Score (Test) | 89.28% | 94.25% |

* **Custom CNN Performance**: The model performed well across most classes but exhibited weakness in the 'cat' class (Precision: 0.79, Recall: 0.79).
* **ResNet-18 Performance**: This model demonstrated exceptionally high and consistent performance across all classes, unlike the custom model.

## 📰 **Conclusion**
1.  The modified ResNet-18 model significantly outperformed the custom CNN, achieving a **test accuracy of 94.25%** compared to the custom model's 89.26%. However, the ResNet-18 model's high training accuracy (99.92%) suggests it is prone to overfitting.
2.  The deeper architecture of ResNet-18, combined with its use of **residual blocks**, proved more effective at extracting the complex features necessary for accurate CIFAR-10 classification.

## 🙍‍♂️ **Contributors**
- Alif Alamsyah (11220940000028)
- Ibnullabib (11220940000037)
