# 🧠 Introduction to Deep Learning Architectures

**Deep Learning (DL)** is a subset of machine learning that uses neural networks with many layers (hence "deep") to model complex patterns in data. It enables breakthroughs in areas such as image recognition, natural language processing, and autonomous systems.

---

## 🔁 How Deep Learning Works: Forward & Backpropagation

### ✅ Forward Propagation

- Input data passes through the layers of the neural network.
- Each layer computes a transformation: `Z = W·X + b`
- An activation function (like ReLU or Sigmoid) is applied.
- The final output is the model's prediction.

### 🔁 Backpropagation

- Compares prediction to ground truth using a loss function (e.g., MSE, Cross-Entropy).
- Calculates gradients of loss with respect to weights using the **chain rule**.
- Gradients are propagated **backward** through the network.
- Weights are updated using an optimizer like **SGD** or **Adam**.

> Together, forward and backward propagation form one **training step** (i.e., a single batch update during learning).

---

## 📚 Architectures Covered

This section introduces the **three foundational architectures** in deep learning:

---

## 1️⃣ Artificial Neural Networks (ANN / MLP)

**Use Case**: Tabular data, simple pattern recognition

- Fully connected (dense) layers  
- No spatial or sequential awareness  
- Often used for:
  - Classification on structured data (e.g., Iris dataset)
  - Regression problems

**Typical Layers**:
Input → Dense → Activation → Dense → Output


---

## 2️⃣ Convolutional Neural Networks (CNN)

**Use Case**: Image and spatial data

- Uses **convolutional layers** to detect spatial patterns (edges, textures)  
- **Pooling layers** reduce dimensionality  
- **Flattened** and passed to fully connected layers

**Common Applications**:
- Image classification (e.g., MNIST, CIFAR-10)
- Object detection
- Medical imaging

**Typical Layers**:
Input Image → Conv2D → ReLU → MaxPooling → ... → Flatten → Dense → Output


---

## 3️⃣ Recurrent Neural Networks (RNN)

**Use Case**: Sequential or time-series data

- Maintains **memory of previous inputs** using hidden states  
- Processes one element of a sequence at a time  
- Variants include **LSTM** and **GRU** for long-term dependencies

**Common Applications**:
- Sentiment analysis
- Speech recognition
- Stock price forecasting

**Typical Layers**:
Sequence Input → RNN/LSTM/GRU Layer → Dense → Output

---

## 📌 Summary Table

| Architecture | Best For             | Strengths                   | Limitations                  |
|--------------|----------------------|-----------------------------|------------------------------|
| **ANN**      | Tabular/classical ML | Simple and versatile        | No spatial/sequential logic |
| **CNN**      | Images, videos       | Captures spatial features   | Not good for sequences       |
| **RNN**      | Text, time series    | Handles temporal patterns   | Training instability, slow   |

---

> 🚀 We'll build and train models using all three types using PyTorch and real datasets.
