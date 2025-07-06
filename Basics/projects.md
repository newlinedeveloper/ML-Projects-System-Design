## 🧠 1. **Supervised Learning**

### 🔸 A. Linear Regression

* **Use Case**: Predict continuous values
* **Project**: House Price Prediction

```python
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
from sklearn.datasets import fetch_california_housing
import matplotlib.pyplot as plt

data = fetch_california_housing()
X_train, X_test, y_train, y_test = train_test_split(data.data, data.target, test_size=0.2)

model = LinearRegression()
model.fit(X_train, y_train)

print("Predicted:", model.predict(X_test[:5]))
print("Actual:", y_test[:5])
```

---

### 🔸 B. Logistic Regression

* **Use Case**: Binary classification (0/1)
* **Project**: Email Spam Detection

```python
from sklearn.linear_model import LogisticRegression
from sklearn.datasets import load_digits
from sklearn.model_selection import train_test_split
from sklearn.metrics import classification_report

digits = load_digits()
X = digits.data
y = (digits.target == 1).astype(int)  # classify digit '1' vs rest

X_train, X_test, y_train, y_test = train_test_split(X, y)

model = LogisticRegression(max_iter=2000)
model.fit(X_train, y_train)

print(classification_report(y_test, model.predict(X_test)))
```

---

### 🔸 C. Decision Tree Classifier

* **Use Case**: Rule-based classification
* **Project**: Medical Diagnosis

```python
from sklearn.tree import DecisionTreeClassifier
from sklearn.datasets import load_breast_cancer
from sklearn.model_selection import train_test_split

X, y = load_breast_cancer(return_X_y=True)
X_train, X_test, y_train, y_test = train_test_split(X, y)

tree = DecisionTreeClassifier(max_depth=3)
tree.fit(X_train, y_train)

print("Accuracy:", tree.score(X_test, y_test))
```

---

### 🔸 D. Random Forest

* **Use Case**: Ensemble classification
* **Project**: Customer Churn Prediction

```python
from sklearn.ensemble import RandomForestClassifier
from sklearn.datasets import load_wine
from sklearn.model_selection import train_test_split

X, y = load_wine(return_X_y=True)
X_train, X_test, y_train, y_test = train_test_split(X, y)

rf = RandomForestClassifier()
rf.fit(X_train, y_train)

print("Accuracy:", rf.score(X_test, y_test))
```

---

### 🔸 E. Support Vector Machines (SVM)

* **Use Case**: Max-margin binary classification
* **Project**: Face Recognition (on small image datasets)

```python
from sklearn import svm
from sklearn.datasets import load_digits
from sklearn.model_selection import train_test_split

X, y = load_digits(return_X_y=True)
X_train, X_test, y_train, y_test = train_test_split(X, y)

model = svm.SVC(kernel='linear')
model.fit(X_train, y_train)

print("Test Accuracy:", model.score(X_test, y_test))
```

---

### 🔸 F. K-Nearest Neighbors (KNN)

* **Use Case**: Instance-based learning
* **Project**: Handwritten Digit Recognition (MNIST-style)

```python
from sklearn.neighbors import KNeighborsClassifier
from sklearn.datasets import load_digits
from sklearn.model_selection import train_test_split

X, y = load_digits(return_X_y=True)
X_train, X_test, y_train, y_test = train_test_split(X, y)

model = KNeighborsClassifier(n_neighbors=3)
model.fit(X_train, y_train)

print("Accuracy:", model.score(X_test, y_test))
```

---

## 🔍 2. **Unsupervised Learning**

### 🔸 A. K-Means Clustering

* **Use Case**: Grouping similar items
* **Project**: Customer Segmentation

```python
from sklearn.cluster import KMeans
from sklearn.datasets import make_blobs
import matplotlib.pyplot as plt

X, _ = make_blobs(n_samples=300, centers=4, random_state=42)

kmeans = KMeans(n_clusters=4)
kmeans.fit(X)

plt.scatter(X[:, 0], X[:, 1], c=kmeans.labels_)
plt.scatter(kmeans.cluster_centers_[:, 0], kmeans.cluster_centers_[:, 1], c='red')
plt.title("Customer Segments")
plt.show()
```

---

### 🔸 B. PCA (Principal Component Analysis)

* **Use Case**: Dimensionality reduction
* **Project**: Visualizing high-dimensional data

```python
from sklearn.decomposition import PCA
from sklearn.datasets import load_digits
import matplotlib.pyplot as plt

X, y = load_digits(return_X_y=True)
pca = PCA(n_components=2)
X_pca = pca.fit_transform(X)

plt.scatter(X_pca[:, 0], X_pca[:, 1], c=y, cmap="Spectral", s=15)
plt.title("PCA - Digits")
plt.show()
```

---

## 🤖 3. **Reinforcement Learning (Intro)**

### 🔸 Q-Learning (simplified)

* **Use Case**: Game AI
* **Project**: Grid world agent

```python
import numpy as np

states = 5
actions = 2
Q = np.zeros((states, actions))
alpha = 0.1
gamma = 0.9

for episode in range(1000):
    s = np.random.randint(0, states)
    a = np.random.choice([0, 1])
    reward = 1 if s == 4 and a == 1 else 0
    next_s = (s + 1) % states
    Q[s, a] = Q[s, a] + alpha * (reward + gamma * max(Q[next_s]) - Q[s, a])

print("Q-table:\n", Q)
```

---

## 📚 4. **Natural Language Processing (NLP)**

### 🔸 Logistic Regression on TF-IDF

* **Use Case**: Sentiment Analysis
* **Project**: Movie Review Classifier

```python
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.linear_model import LogisticRegression

texts = ["I loved the movie", "Horrible movie", "Best film ever", "Waste of time"]
labels = [1, 0, 1, 0]

vec = TfidfVectorizer()
X = vec.fit_transform(texts)

model = LogisticRegression()
model.fit(X, labels)

print("Predicted:", model.predict(vec.transform(["Amazing movie"])))
```

---

## 🤯 5. **Deep Learning (Bonus)**

### 🔸 BERT for Toxic Comment Classification

* **Use Case**: Harmful Content Detection
* **Project**: Classify toxic comments on social media

```python
# pip install transformers
from transformers import pipeline
classifier = pipeline("text-classification", model="unitary/toxic-bert")

result = classifier("I hate you so much!")
print(result)
```

---


