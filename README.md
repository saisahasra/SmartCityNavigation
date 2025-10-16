# 🏙️ SmartCityNav

**SmartCityNav** is a Python-based project that applies Artificial Intelligence and Machine Learning techniques to optimise delivery routes in a simulated smart city.  
It compares predictive models and pathfinding algorithms to estimate traversal costs across city grids and implements a reinforcement learning (Q-learning) agent for autonomous navigation.

---

## 📘 Project Overview

The project explores how AI can be used to enhance delivery efficiency in complex urban environments.

**Main Components:**
1. Predicting traversal costs across a city grid using regression and neural network models.  
2. Comparing search algorithms to determine the most efficient route.  
3. Training a self-driving taxi agent using Q-learning to navigate a grid world while avoiding obstacles.

This project aligns with real-world applications in logistics, smart cities, and autonomous systems.

---

## 🧩 Problem Context

Delivery companies in modern smart cities face challenges such as:
- Traffic congestion  
- Poor road conditions  
- Changing weather  
- High population density  

Optimizing delivery routes reduces operational costs, enhances customer satisfaction, and minimizes environmental impact.

---

## 🎯 Objectives

1. **Estimate traversal costs** for each cell in a city grid based on environmental and infrastructural factors.  
2. **Compare multiple AI models** (Linear Regression, Polynomial Regression, Neural Networks) for accuracy and performance.  
3. **Evaluate search algorithms** (DFS, BFS, Dijkstra’s, and A*) to identify the most efficient routing method.  
4. **Implement a Q-learning agent** to simulate intelligent navigation in a grid environment.

---

## 🧠 Tasks Overview

### **Task 1: Problem Analysis**
- Discusses the importance of optimizing deliveries in urban environments.  
- Explores how AI can assist through prediction and search.  
- Defines whether the problem is predictive, search-based, or both.  
- Concludes that the task involves **regression-based prediction** combined with **search algorithms**.

---

### **Task 2: Predictive Modelling**

**Data:** `traversal_cost_data.csv`

#### Models Implemented:
1. **Linear Regression**  
   - Simple, interpretable, but underfits complex relationships.  
   - **MAE:** 124.31 | **RMSE:** 165.67  

2. **Polynomial Regression (Degree 4)**  
   - Captures non-linear trends effectively but is prone to overfitting.  
   - **MAE:** 0.43 | **RMSE:** 0.54  

3. **Neural Network**  
   - Handles multiple features and complex interactions efficiently.  
   - **MAE:** 3.30 | **RMSE:** 4.38  

#### Result:
While the **Polynomial Regression model** produced the lowest errors, the **Neural Network model** was the most suitable for scalability and handling multiple features.

---

### **Task 3: Route Optimisation**

Using the **Neural Network model**, traversal costs were estimated for each grid cell (`provided_grid.csv`) and stored in `Estimated_grid.csv`.

#### Pathfinding Algorithms Compared:

| Algorithm | Description | Pros | Cons | Suitable For |
|------------|-------------|------|------|---------------|
| **DFS** | Explores deep paths first | Low memory use | Doesn’t guarantee shortest path | Small graphs |
| **BFS** | Explores all neighbors first | Guarantees shortest path (unweighted) | Memory intensive | Unweighted graphs |
| **Dijkstra’s** | Finds shortest path in weighted graphs | Guarantees optimal path | Slower on dense graphs | Weighted grids |
| **A\*** | Uses heuristics + weights | Fast and optimal with good heuristic | Depends on heuristic quality | Weighted graphs with known goal |

**Recommendation:**  
**A\* Search Algorithm** – balances optimality and efficiency using heuristics for weighted, goal-oriented navigation.

---

### **Task 4: Q-Learning (Reinforcement Learning)**

A self-driving taxi agent is trained to navigate a 5×5 grid world:  
- **Start:** (1, 1)  
- **Goal:** (5, 5)  
- **Obstacles:** (2, 2) and (4, 4)  
- **Rewards:**  
  - +100 for reaching the goal  
  - -10 for hitting the obstacle  
  - +1 for valid moves  

#### Highlights:
- Implemented epsilon-greedy exploration with decay.  
- Trained over 1000 episodes.  
- Visualised policy and learning progress.  
- Achieved a strong policy that efficiently reaches the goal while avoiding penalties.

---

## ⚙️ Technologies Used

- **Programming Language:** Python  
- **Libraries:**  
  - `pandas`, `numpy`, `matplotlib` – Data handling and visualisation  
  - `scikit-learn` – Regression and preprocessing  
  - `tensorflow / keras` – Neural network training  
- **Algorithms:**  
  - Linear Regression  
  - Polynomial Regression  
  - Neural Network  
  - DFS, BFS, Dijkstra’s, A*  
  - Q-learning

---
