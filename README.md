# Applied Deep Learning (APA 2024) – Practical Projects 🧠💻

This repository contains the practical assignments developed for the course **Applied Deep Learning (APA)** at the University of Coimbra. The course provides a hands-on introduction to deep learning with a focus on computer vision and robotics applications.

Each assignment explores different deep learning concepts, from classification and feature extraction to reinforcement learning and object detection.

## 📚 Overview

| Assignment | Topic                                              | Main Techniques                                |
|------------|----------------------------------------------------|------------------------------------------------|
| [TP1](./tp1_cnn_fusion_classification) | CNN Design and Middle Fusion                    | Custom CNNs, Transfer Learning, Model Fusion   |
| [TP2](./tp2_autoencoders_yolo)         | Autoencoders and Object Detection               | AE, VAE, DAE, YOLOv5, Transfer Learning        |
| [TP3](./tp3_deep_rl_control)           | Deep Reinforcement Learning for Agent Control   | DQN, Double DQN, Dueling DQN, CNN, MLP         |

---

## 🔧 Technologies Used

- Python 3.10
- PyTorch
- torchvision
- scikit-learn
- matplotlib, seaborn
- OpenAI Gym
- Ultralytics YOLOv5

---

## 🧠 Assignment Summaries

### 🧩 [TP1 – CNNs and Feature Fusion](./tp1_cnn_fusion_classification)

- Designed and optimized a custom CNN for the CIFAR-10 dataset (3 versions: base, V2, V3).
- Trained **AlexNet** and **MobileNetV2** on **EuroSAT**, using both random initialization and pretrained weights.
- Developed a **Middle Fusion model** combining features from both networks.
- Evaluated performance with accuracy, F1-score, confusion matrices.

### 🧠 [TP2 – Autoencoders and YOLOv5](./tp2_autoencoders_yolo)

- Implemented **AE**, **VAE**, and **DAE** on FashionMNIST for image reconstruction and classification.
- Visualized latent spaces and assessed robustness to noise.
- Used encoder bottlenecks as feature extractors for classifiers.
- Trained **YOLOv5s** on a custom KITTI subset, comparing training from scratch and transfer learning.

### 🤖 [TP3 – Deep Reinforcement Learning](./tp3_deep_rl_control)

- Applied DQN, Double DQN and Dueling DQN to control a car in the **CarRacing-v2** environment.
- Used a custom CNN as a Q-network for both continuous and discrete actions.
- Transferred the best-performing model to a **custom mobile robot environment**, evaluating two observation modes: PoseOnly and Pose+Map.
- Designed a custom MLP for low-dimensional state input.

---

## 🧑‍💻 Authors

- Gonçalo Bastos – eusoudebastos@gmail.com  
- Leonardo Cordeiro – leoleocordeiro@gmail.com  
University of Coimbra – M.Sc. in Electrical and Computer Engineering

---

## 📝 License

Each folder contains:
- Source code (Jupyter Notebooks and scripts)
- PDF reports
- Optional results (plots, saved models)

This repository is for academic and educational purposes. Any external datasets (e.g., CIFAR-10, EuroSAT, KITTI) are subject to their respective licenses and terms of use.
