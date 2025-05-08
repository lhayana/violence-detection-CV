# Violence Detection in Videos with ResNet3D-18 and VideoMAE

This project presents a comparative study of two deep learning architectures for automatic violence detection in videos: the convolutional ResNet3D-18 and the transformer-based VideoMAE. Both models were trained and evaluated on a balanced dataset of violent and non-violent video samples.

## Overview

The goal of this project is to evaluate the trade-offs between a lightweight CNN and a more complex transformer in terms of accuracy, computational cost, and generalization capacity. All experiments were conducted using Google Colab with GPU acceleration (NVIDIA A100).

- **ResNet3D-18**: CNN-based model with low complexity and fast training
- **VideoMAE**: Transformer-based model pre-trained with masked autoencoding

## Dataset

I used the [Violence Detection Dataset](https://github.com/airtlab/A-Dataset-for-Automatic-Violence-Detection-in-Videos), provided by the AIRT LAB. The dataset contains videos labeled as "violence" or "non-violence", covering diverse real-world scenarios.

- Source: https://github.com/airtlab/A-Dataset-for-Automatic-Violence-Detection-in-Videos
- Format: Videos organized by class and split into train, validation, and test sets
- Preprocessing: Frames extracted and resized, with optional augmentation

## Setup

### Requirements

- Python 3.10
- PyTorch
- TorchVision
- Transformers (Hugging Face)
- OpenCV
- Gradio
