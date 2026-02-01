# Color-Channel-Perturbation-Attack
This project studies Color Channel Perturbation (CCP), a stochastic, data-independent attack that exploits CNN sensitivity to color distributions. CCP significantly degrades classification and object detection performance on CIFAR-10, Caltech256, and COCO. We evaluate VGG16, ResNet56, and YOLO, and propose defense strategies using CCP-based data augmentation and kriging-based restoration.

Overview

Convolutional Neural Networks (CNNs) achieve high accuracy in computer vision tasks but are highly sensitive to color distributions in images. This project explores Color Channel Perturbation (CCP), a stochastic and data-independent attack that exploits this vulnerability by altering color channel compositions. We evaluate how CCP affects image classification and object detection models and propose defense strategies to improve robustness.

Problem Statement

Develop and evaluate CNN models that can maintain reliable performance under color-based image transformations and adversarial perturbations, without significant degradation in classification or detection accuracy.

Color Channel Perturbation (CCP) Attack

CCP generates transformed images by recombining RGB channels using stochastic weights.

Key Characteristics:

Data-independent stochastic attack

Uniform transformation applied across all pixels in an image

Preserves local spatial structure while altering color distributions

Uses scale and bias parameters to control visual appearance

CCP Variants:

Fixed CCP (CCP-F): Same random weights applied to all test images

Variable CCP (CCP-V): Different random weights generated per test image

Models Evaluated

VGG16: Deep CNN with 16 learnable layers

ResNet56: Residual architecture enabling deeper networks

YOLO: End-to-end object detection model for real-time inference

Datasets Used

CIFAR-10: 60,000 images, 10 classes, 32×32 resolution

Caltech256: 30,607 images, 257 classes, 256×256 resolution

COCO: Used for evaluating object detection under CCP attacks

Defense Mechanisms
1. CCP-Based Data Augmentation

Augments training data with CCP-attacked images

Improves robustness to color perturbations

Increases training time and computational cost

2. Kriging-Based Image Restoration

Statistical interpolation method derived from Sequential Gaussian Simulation (SGS)

Estimates pixel intensities using spatial covariance

Reduces CCP artifacts while preserving image structure

Computationally efficient compared to full SGS

3. Adaptive Median Filtering

Applied after kriging to reduce residual noise

Helps restore visual consistency in transformed images

Results & Observations

Significant accuracy drop observed under CCP attacks for VGG16 and ResNet56

High-confidence predictions on clean images become incorrect after CCP

Object detection performance using YOLO degrades under CCP, with missed detections and reduced confidence

Data augmentation and kriging improve robustness, but do not fully eliminate CCP impact
