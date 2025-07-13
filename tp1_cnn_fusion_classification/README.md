# TP1 – Image Classification with CNNs and Middle Fusion 🧠🛰️

This project explores the implementation and optimization of Convolutional Neural Networks (CNNs) for image classification tasks using the CIFAR-10 and EuroSAT datasets. It is divided into two main parts: the design of a custom CNN from scratch and the use of transfer learning with a middle fusion strategy.

<img width="791" height="1760" alt="image" src="https://github.com/user-attachments/assets/aa2819d5-6613-46b7-abfb-1ec4fd17fd35" />

<img width="820" height="1760" alt="image" src="https://github.com/user-attachments/assets/c2faa1ef-7454-4952-b0bf-12cfcc215c49" />


---

## 🧩 Part I – Custom CNN on CIFAR-10

A CNN was built from scratch to classify RGB images from the CIFAR-10 dataset into 10 distinct object categories. Three versions of the model were developed:

- **Base model** – simple 3-layer CNN
- **CNNV2** – increased filters, added batch norm, dropout, and pooling
- **CNNV3** – 5 convolutional layers with progressive dropout and L2 regularization

### Architecture Overview

- Convolutional layers with ReLU activations  
- Batch normalization and dropout  
- Max pooling  
- Fully connected layers for classification  

### Performance Summary

| Model   | Validation Accuracy (%) | Notes                              |
|---------|--------------------------|-------------------------------------|
| Base    | 61.6                     | Clear overfitting                   |
| CNNV2   | 75.0                     | Better generalization               |
| CNNV3   | **83.13**                | Best performance with regularization |

Four sets of hyperparameters were tested, tuning `dropout`, `learning rate`, and `weight decay`.

---

## 🌍 Part II – Transfer Learning and Middle Fusion on EuroSAT

In the second part, pre-trained CNN models were applied to the EuroSAT dataset, which contains satellite imagery classified into 10 land use categories.

### Models and Strategy

- **AlexNet** and **MobileNetV2**, trained from scratch and using pre-trained ImageNet weights
- A **Middle Fusion** model combining feature maps from both pre-trained networks

The fusion strategy involved:

- Removing the classification heads  
- Extracting and aligning feature maps  
- Concatenating the features and feeding them into a new classifier  

### Performance Summary

| Model                     | Validation Accuracy (%) |
|---------------------------|--------------------------|
| AlexNet (from scratch)    | ~70                      |
| MobileNetV2 (from scratch)| ~72                      |
| AlexNet (pre-trained)     | ~75                      |
| MobileNetV2 (pre-trained) | ~78                      |
| **Middle Fusion**         | **~82–83**                |

The fusion approach demonstrated significant performance improvements, highlighting the benefit of combining feature representations from multiple architectures.

---

## 📁 Folder Contents

- `APA_ASSIG1_FINAL.ipynb` — Jupyter notebook with full implementation  
- `APA_Assign1_Goncalo_Bastos_Leonardo_Cordeiro.pdf` — technical report  
- `results/` — figures such as confusion matrices and training curves  

---

## 👨‍💻 Authors

- Gonçalo Bastos – eusoudebastos@gmail.com  
- Leonardo Cordeiro – leoleocordeiro@gmail.com  
University of Coimbra – Electrical and Computer Engineering
