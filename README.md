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

## Project Structure

- `dataset_preprocessing/` – Frame extraction and dataset organization
- `models/` – Model definitions and configurations
- `training/` – Training loops, optimizers, early stopping, precision settings
- `evaluation/` – Scripts for computing metrics and generating confusion matrices
- `inference/` – Gradio-based interface for testing trained models

## Results

The models were trained on the same dataset and evaluated on a held-out test set. The key performance metrics for the **positive class (violence)** are summarized below:

| Metric        | ResNet3D-18 | VideoMAE  |
|---------------|-------------|-----------|
| Accuracy      | 88%         | 68%       |
| Precision     | 88%         | 75%       |
| Recall        | 89%         | 54%       |
| F1-score      | 89%         | 63%       |
| Training Time | 2 minutes   | 39 minutes |

## Analysis

The ResNet3D-18 model outperformed VideoMAE in all classification metrics, particularly in recall, which is critical for detecting violent content. It also required significantly less computational time and resources.

While VideoMAE offers a more powerful architecture capable of modeling temporal relationships, its performance in this experiment was limited by data size and sensitivity to hyperparameter tuning. The results suggest that transformer-based models like VideoMAE may only reach their full potential when trained on large-scale video datasets with extensive optimization.

## Conclusion

This project shows that simpler models like ResNet3D-18 can be highly effective for structured visual tasks, particularly when computational resources or dataset size are limited. Transformer-based architectures such as VideoMAE are promising alternatives for more complex scenarios but require careful tuning and sufficient data to be competitive.

## License

This project is intended for academic and research use. The dataset is governed by its original license from [AIRT LAB](https://github.com/airtlab/A-Dataset-for-Automatic-Violence-Detection-in-Videos).

## Acknowledgments

- [AIRT LAB – Violence Detection Dataset](https://github.com/airtlab/A-Dataset-for-Automatic-Violence-Detection-in-Videos)
- [VideoMAE model (Hugging Face)](https://huggingface.co/facebook/videomae-base)
- [ResNet paper (He et al., 2016)](https://arxiv.org/abs/1512.03385)
