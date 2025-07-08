# TP3 – Deep Reinforcement Learning for Agent Control 🚗🤖

This project explores the use of **Deep Reinforcement Learning (DeepRL)** to control agents in simulated environments, focusing on state representations based on images and pose vectors.

## 🧩 Part I — OpenAI CarRacing-v2

A custom CNN was implemented and integrated with:

- DQN  
- Double DQN  
- Dueling DQN  
- Double Dueling DQN  

### 🎮 Control modes:
- **Continuous control** (3 variables: steering, gas, brake)  
- **Discrete control** (5 actions: nothing, left, right, gas, brake)  

### 🔧 CNN Architecture
- 3 convolutional layers (32→64 filters) + GELU + MaxPooling  
- Final fully connected layers  
- Dueling variant: separate branches for `Value` and `Advantage`

### 📊 Performance Summary (example)

| Model           | Mode      | Avg. Normal Tracks | Avg. Random Tracks |
|------------------|-----------|---------------------|---------------------|
| DQN              | Continuous | ~840                | ~-57                |
| Dueling DQN      | Discrete   | **~810**            | ~-42                |

> The best overall performance was achieved with **Dueling DQN using discrete control**.

---

## 🤖 Part II — Custom Environment (Mobile Robot)

The best-performing model from Part I (Dueling DQN – discrete mode) was applied to a custom environment to control a mobile robot in two scenarios:

1. **PoseOnly** – input: vector indicating the direction to the goal  
2. **PoseAndLocalMap** – input: pose + flattened local map with obstacle information  

### 🔧 MLP Architecture
- 3 linear layers with GELU activations  
- Separate branches for Value and Advantage streams  
- Q(s,a) = V(s) + (A(s,a) - mean(A(s,a)))

### 📈 Observations

| Scenario            | Episodes to Stabilize | Avg. Reward |
|---------------------|-----------------------|-------------|
| PoseOnly            | ~300                  | still negative |
| PoseAndLocalMap     | ~1000–1500            | ~-200         |

> The agent learned to avoid obstacles and reach the goal, though longer training and better regularization may improve consistency.

---

## 📁 Directory Contents

- `APA_Assign3_Goncalo_Bastos_Leonardo_Cordeiro.pdf` — technical report  
- `APA2024_DeepRL_Part1.ipynb` — full implementation of part1
-  `APA2024_DeepRLPart2.ipynb` — full implementation of part2
- `results/` — training plots, visual results and GIFS or videos

---

## 👨‍💻 Authors

- Gonçalo Bastos – eusoudebastos@gmail.com  
- Leonardo Cordeiro – leoleocordeiro@gmail.com  
University of Coimbra – Electrical and Computer Engineering

