## Machine Learning (ML)

---

## 📚 1. Categories of Machine Learning

| Category                     | Description                                            |
| ---------------------------- | ------------------------------------------------------ |
| **Supervised Learning**      | Train with labeled data (input → output)               |
| **Unsupervised Learning**    | Train with only input data (no labels)                 |
| **Semi-supervised Learning** | Mix of labeled and unlabeled data                      |
| **Reinforcement Learning**   | Agent learns by interacting with environment (rewards) |

---

## ✅ 2. Supervised Learning Algorithms

### 2.1. 🔢 Linear Regression

* **Goal**: Predict continuous values
* **How it works**: Fits a straight line `y = mx + b`
* **Use cases**: House price, salary prediction

```python
from sklearn.linear_model import LinearRegression
model = LinearRegression()
model.fit(X_train, y_train)
preds = model.predict(X_test)
```

---

### 2.2. 🔢 Logistic Regression

* **Goal**: Binary classification (0/1)
* **How it works**: Uses sigmoid function to model probability
* **Use cases**: Spam detection, disease prediction

```python
from sklearn.linear_model import LogisticRegression
model = LogisticRegression()
model.fit(X_train, y_train)
preds = model.predict(X_test)
```

---

### 2.3. 🌳 Decision Tree

* **Goal**: Classification or regression
* **How it works**: Tree-like structure splitting on features
* **Use cases**: Credit approval, medical diagnosis

```python
from sklearn.tree import DecisionTreeClassifier
model = DecisionTreeClassifier()
model.fit(X_train, y_train)
```

---

### 2.4. 🌲 Random Forest

* **Goal**: Ensemble of decision trees
* **How it works**: Aggregates multiple trees to reduce overfitting
* **Use cases**: Fraud detection, stock prediction

```python
from sklearn.ensemble import RandomForestClassifier
model = RandomForestClassifier()
model.fit(X_train, y_train)
```

---

### 2.5. 💡 Support Vector Machine (SVM)

* **Goal**: Classification
* **How it works**: Finds hyperplane that best separates classes
* **Use cases**: Face detection, text categorization

```python
from sklearn.svm import SVC
model = SVC()
model.fit(X_train, y_train)
```

---

### 2.6. 🧠 K-Nearest Neighbors (KNN)

* **Goal**: Classification or regression
* **How it works**: Predicts based on k nearest data points
* **Use cases**: Recommender systems, pattern recognition

```python
from sklearn.neighbors import KNeighborsClassifier
model = KNeighborsClassifier(n_neighbors=3)
model.fit(X_train, y_train)
```

---

## 🔍 3. Unsupervised Learning Algorithms

### 3.1. 📊 K-Means Clustering

* **Goal**: Group data into clusters
* **How it works**: Minimizes distance to cluster centroids
* **Use cases**: Customer segmentation, image compression

```python
from sklearn.cluster import KMeans
model = KMeans(n_clusters=3)
model.fit(X)
```

---

### 3.2. 🕸️ Hierarchical Clustering

* **Goal**: Build nested clusters
* **How it works**: Merge or split clusters based on distance
* **Use cases**: Social network analysis, gene expression

```python
from scipy.cluster.hierarchy import dendrogram, linkage
import matplotlib.pyplot as plt
linked = linkage(X, 'ward')
dendrogram(linked)
plt.show()
```

---

### 3.3. 📉 Principal Component Analysis (PCA)

* **Goal**: Dimensionality reduction
* **How it works**: Projects data onto fewer orthogonal components
* **Use cases**: Data compression, visualization

```python
from sklearn.decomposition import PCA
pca = PCA(n_components=2)
X_reduced = pca.fit_transform(X)
```

---

## 🎓 4. Semi-Supervised Learning

* **Combines**: Small labeled + large unlabeled data
* **Common methods**:

  * Self-training
  * Label propagation

**Example**:

```python
from sklearn.semi_supervised import LabelSpreading
model = LabelSpreading()
model.fit(X, y)  # y can contain -1 for unlabeled
```

---

## 🧠 5. Reinforcement Learning (Intro)

* **Agent learns by interacting**
* **Core concepts**:

  * Environment
  * Reward
  * Policy
  * Q-values

**Popular algorithms**:

* Q-Learning
* Deep Q-Network (DQN)
* Proximal Policy Optimization (PPO)

Example with `gym`:

```python
import gym
env = gym.make("CartPole-v1")
obs = env.reset()
for _ in range(1000):
    action = env.action_space.sample()
    obs, reward, done, _ = env.step(action)
    if done:
        break
```

---

## 📦 6. Popular Libraries

| Library      | Purpose           |
| ------------ | ----------------- |
| Scikit-learn | Classic ML        |
| XGBoost      | Gradient boosting |
| LightGBM     | Fast tree models  |
| TensorFlow   | Deep learning     |
| PyTorch      | Deep learning     |
| HuggingFace  | NLP models        |
| OpenCV       | Computer Vision   |

---

## 🚀 7. Suggested Learning Path

1. **Basics**: Python, Pandas, NumPy, Matplotlib
2. **Supervised Learning** (classification, regression)
3. **Unsupervised Learning** (clustering, PCA)
4. **Model Evaluation**: accuracy, precision, recall, ROC
5. **Feature Engineering**: scaling, encoding, selection
6. **Deep Learning**: CNNs, RNNs, Transformers
7. **Deployment**: Flask/FastAPI + Docker + CI/CD
8. **Advanced Topics**: AutoML, RL, Explainability

---

