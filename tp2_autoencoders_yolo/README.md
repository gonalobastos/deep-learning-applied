# TP2 – Autoencoders and Object Detection with YOLOv5 🔍🧠

This project is divided into two main parts:
1. **Image reconstruction and noise removal using Autoencoders**
2. **Object detection using YOLOv5, comparing training from scratch vs. transfer learning**

<p align="center">
  <img src="https://github.com/user-attachments/assets/30530637-a69b-4e93-af3c-a9e9990a44d5" alt="results for DAE" width="50%">
</p>

<p align="center">
  <em>Figure: Results for DAE</em>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/8a2d6e89-3070-40f5-9945-2170b391a0e0" alt="detection results with pretrained weights" width="80%">
</p>

<p align="center">
  <em>Figure: Detection results with pre-trained weights</em>
</p>

---

## 🧩 Part I — Autoencoders on FashionMNIST

We implemented and evaluated three types of autoencoders:

- **AE** (Autoencoder)
- **VAE** (Variational Autoencoder)
- **DAE** (Denoising Autoencoder)

### 🛠️ Architectures

- **AE** and **DAE**: convolutional encoder–decoder structure.
- **VAE**: bottleneck generates mean and variance vectors (μ, logσ²); uses the reparameterization trick and KL Divergence.
- **DAE**: trained with added Gaussian noise to the input images.

### 📊 Reconstruction Results

| Model | Reconstruction Loss | Robustness to Noise | Latent Space | Best Use Case |
|-------|---------------------|----------------------|--------------|----------------|
| AE    | Low (0.0058)        | Weak                 | Clear        | Clean data     |
| VAE   | High (5.13)         | Moderate             | Structured   | Latent sampling |
| DAE   | Low (0.0141)        | Strong               | Separated    | Noisy input     |

### 🔍 Latent Space Visualization

All encoders were evaluated with **t-SNE** projections. AE and DAE showed strong class separability, while VAE showed smoother transitions.

---

## 🧠 Part I – Classification with Encoders

Each encoder's bottleneck representation was used as a feature extractor for a classifier:

- **Frozen encoder weights** (`torch.no_grad()`)
- Fully connected layers on top
- Evaluated using accuracy, precision, recall, F1-score

| Model | Accuracy | Precision | Recall | F1-score |
|-------|----------|-----------|--------|----------|
| AE    | 88.04%   | 88.06%    | 88.04% | 87.98%   |
| VAE   | 87.17%   | 87.27%    | 87.17% | 87.11%   |
| DAE   | 86.81%   | 86.70%    | 86.81% | 86.72%   |

> AE achieved the best classification performance due to its deterministic and detailed latent representations.

---

## 🚗 Part II — Object Detection with YOLOv5 (KITTI Dataset)

We trained **YOLOv5s** on a custom KITTI subset to detect only the "car" class.

### ⚙️ Scenarios

- **Training from Scratch**
- **Transfer Learning** (pre-trained weights)

### 📈 Results

| Metric        | Transfer Learning | From Scratch | Observation |
|---------------|-------------------|--------------|-------------|
| Precision     | 0.80              | 0.60         | Fewer false positives |
| Recall        | 0.60              | 0.40         | Higher detection rate |
| mAP@0.5       | 0.55              | 0.50         | Faster convergence with TL |
| mAP@0.5:0.95  | 0.30              | 0.25         | Better localization with TL |

> Transfer learning significantly improved object detection performance compared to training from scratch.

---

## 📁 Directory Contents

- `APA_Assign2_Goncalo_Bastos_Leonardo_Cordeiro.pdf` – full report
- `autoencoders_classification.ipynb` – notebook for Part I
- `yolov5_training/` – training scripts, models, and configs for Part II
- `results/` – plots and visualizations (latent space, reconstructions, confusion matrices)
- `models/` – optionally include trained `.pt` models

---

## 👨‍💻 Authors

- Gonçalo Bastos – eusoudebastos@gmail.com  
- Leonardo Cordeiro – leoleocordeiro@gmail.com  
University of Coimbra – Electrical and Computer Engineering

