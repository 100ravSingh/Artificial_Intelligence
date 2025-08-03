# 📘 Introduction to Machine Learning

Machine Learning (ML) is a subfield of artificial intelligence that gives computers the ability to learn from data without being explicitly programmed. It powers many modern technologies like recommendation systems, fraud detection, and autonomous vehicles.

---

## 🧠 Core ML Paradigms

### 1. Supervised Learning
- **Definition**: Learn a function from input-output pairs.
- **Goal**: Predict labels for new data.
- **Examples**:
  - Regression: Predicting house prices
  - Classification: Email spam detection

### 2. Unsupervised Learning
- **Definition**: Discover patterns or structure in data without labels.
- **Goal**: Group or compress data.
- **Examples**:
  - Clustering: Customer segmentation
  - Dimensionality Reduction: PCA

### 3. Reinforcement Learning (RL)
- **Definition**: Learn by interacting with an environment.
- **Goal**: Maximize long-term reward through trial-and-error.
- **Examples**: Game playing agents, robotics

---

## 🔁 Typical ML Workflow

1. **Data Collection** – Gather raw data from various sources  
2. **Data Preprocessing** – Clean, transform, normalize  
3. **Feature Engineering** – Extract meaningful features  
4. **Model Selection** – Choose suitable algorithm  
5. **Model Training** – Fit the model to training data  
6. **Model Evaluation** – Assess performance on unseen data  
7. **Deployment** – Integrate model into production  
8. **Monitoring** – Track performance & retrain as needed  

---

## 🧰 Tools Used

| Purpose               | Tool               |
|----------------------|--------------------|
| Data Handling        | Pandas, NumPy      |
| Visualization        | Matplotlib, Seaborn|
| ML Models            | Scikit-learn       |
| Deployment (optional)| Streamlit, FastAPI |

---

## 📘 Learning Outcomes

By the end of this module, you should be able to:

- Explain ML paradigms and workflows  
- Apply supervised learning on structured data  
- Evaluate model performance using metrics  
- Build a complete ML pipeline with Scikit-learn  

---

> ℹ️ **Note**: All code examples use `scikit-learn` for model building and evaluation. Please ensure it's installed in your environment using:
> ```bash
> pip install -U scikit-learn
> ```

---

## 📊 Model Evaluation Guide

Understanding how to evaluate models is critical. This section outlines metrics and common remedies for each machine learning paradigm.

---

### 🔢 Supervised Learning

| Task Type         | Evaluation Metric(s)                  | Use Case Example             | Common Fixes                                                                 |
|-------------------|----------------------------------------|-------------------------------|------------------------------------------------------------------------------|
| **Classification** | Accuracy, Precision, Recall, F1, ROC AUC | Spam detection, fraud detection, medical diagnosis | - Use confusion matrix<br>- Tune thresholds<br>- Apply **upsampling** (e.g. SMOTE) or **downsampling** to fix class imbalance<br>- Use ensemble models like Random Forest |
| **Regression**     | MAE, MSE, RMSE, R² Score               | House price prediction, stock forecasting | - Normalize inputs<br>- Remove outliers<br>- Try non-linear models (e.g. polynomial regression, trees)<br>- Feature engineering |

> 💡 **Tip**: Use `imbalanced-learn` (`pip install imbalanced-learn`) for techniques like SMOTE or under/oversampling.

---

### 📉 Unsupervised Learning

| Task Type               | Evaluation Metric(s)                      | Use Case Example             | Common Fixes                                                                 |
|-------------------------|-------------------------------------------|-------------------------------|------------------------------------------------------------------------------|
| **Clustering**          | Silhouette Score, Davies-Bouldin Index    | Customer segmentation         | - Standardize data<br>- Use PCA/t-SNE before clustering<br>- Tune `k`<br>- Try DBSCAN |
| **Dimensionality Reduction** | Visual Inspection (e.g., PCA, t-SNE)     | Visualizing MNIST or Iris     | - Increase number of components<br>- Normalize features<br>- Try nonlinear DR like UMAP or autoencoders |

> 🔍 In clustering tasks without labels, use visualizations and internal metrics like **Silhouette Score** to evaluate.

---

### 🎮 Reinforcement Learning

| Metric                 | Measures                                 | Example                      | Fixes for Low Scores                                                   |
|------------------------|------------------------------------------|-------------------------------|------------------------------------------------------------------------|
| **Average Reward**     | Mean reward per episode                  | CartPole, FrozenLake          | - Train longer<br>- Tune `alpha`, `gamma`, `epsilon`<br>- Improve reward shaping |
| **Win / Success Rate** | Task completion ratio                    | Maze solving, goal-reaching   | - Use more training<br>- Enhance model capacity<br>- Use DQN improvements |
| **Reward Variance**    | Consistency of learned policy            | Any episodic task             | - Clip rewards<br>- Normalize inputs<br>- Reduce exploration noise     |

> 📈 Always plot **reward per episode** to track learning progress and stability.

