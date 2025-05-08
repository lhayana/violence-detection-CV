## Violence Detection in Videos with ResNet3D-18 and VideoMAE

This project presents a comparative study between two deep learning architectures for automatic violence detection in videos: a 3D convolutional neural network (ResNet3D-18) and a transformer-based model (VideoMAE). Both models were trained and evaluated on a labeled dataset containing violent and non-violent video samples.

The ResNet3D-18 model, known for its simplicity and computational efficiency, achieved higher performance with 88% accuracy and an 89% F1-score, demonstrating strong generalization even with limited data. In contrast, the VideoMAE model, despite its advanced architecture and ability to model temporal dependencies, achieved 68% accuracy and a 63% F1-score, with notably lower recall (54%).

The analysis emphasizes the suitability of lightweight CNN-based models for structured visual tasks, while also acknowledging the potential of transformers in more complex scenarios, provided that sufficient data, computational power, and parameter tuning are available. The training was conducted in a GPU-accelerated environment (Google Colab with NVIDIA A100), and the pipeline includes data preprocessing, augmentation, model fine-tuning, and evaluation using classification metrics and confusion matrices.

Final results:
- ResNet3D-18: Faster training (2 minutes), strong generalization, high recall.
- VideoMAE: Longer training (39 minutes), lower recall, greater sensitivity to training conditions.

The full implementation, dataset processing, and evaluation scripts are available in this repository.
