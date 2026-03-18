# K-Means Clustering Visualizer 🔵🟢🔴

![Language](https://img.shields.io/badge/Language-C%2B%2B17-blue)
![Algorithm](https://img.shields.io/badge/Algorithm-K--Means%2B%2B-green)
![Dataset](https://img.shields.io/badge/Dataset-Iris-orange)

> A C++ implementation of K-Means clustering extended with K-Means++ 
> initialization, Elbow Method, CSV support, and ASCII visualization.

---

## ✨ Features

- 📥 **CSV Parser** — loads real datasets like Iris, skips headers and text labels automatically
- 🎯 **K-Means++ Initialization** — smarter centroid seeding, reduces iterations by ~33%
- 📊 **Elbow Method** — automatically suggests optimal K by computing WCSS for K=1 to 8
- 🖥️ **ASCII Visualizer** — displays cluster separation directly in terminal

---

## 🚀 Build and Run

### Requirements
- g++ with C++11 support
- Any CSV dataset (Iris included)

### Compile
```bash
g++ -o kmeans kmeans.cpp -std=c++11
```

### Run
```bash
kmeans.exe iris.csv 3 cluster-details
```

### Arguments
| Argument | Description |
|---|---|
| `iris.csv` | Input dataset file |
| `3` | Number of clusters (K) |
| `cluster-details` | Output directory |

---

## 📊 Sample Output

### Elbow Method
```
WCSS for K=1 : 680.824
WCSS for K=2 : 152.369
WCSS for K=3 : 78.940  ← optimal K
WCSS for K=4 : 57.473
```

### ASCII Visualization (K=3)
```
=== ASCII Cluster Visualization ===
    (Petal Length vs Petal Width)
----------------------------------------------------------------
| ..............................................2..22......... |
| ........................................3....2.............. |
| ........................................222.2.2..22........2 |
| .......................................322..222..2....222... |
| .....................................3.33...22.2.2..2....... |
| .........................3...3333.33........................ |
| ......1..................................................... |
| ...11.1.1................................................... |
| 11.11.1.1................................................... |
----------------------------------------------------------------
  Cluster 1=Setosa  2=Versicolor  3=Virginica
```

---

## 🌸 Dataset

Using the classic [Iris Dataset](https://archive.ics.uci.edu/ml/datasets/iris) — 150 samples, 3 species, 4 features:
- Sepal Length, Sepal Width, Petal Length, Petal Width

The algorithm correctly identifies all 3 species **without any labels** — pure unsupervised learning.

---

## 🛠️ Tech Stack

| Tool | Usage |
|---|---|
| C++11 | Core implementation |
| STL vectors | Data storage |
| File I/O (fstream) | CSV parsing and output |
| OMP pragmas | Parallel distance calculation |

---

## 🧠 What I Extended

This project is forked from [aditya1601/kmeans-clustering-cpp](https://github.com/aditya1601/kmeans-clustering-cpp) and extended with:

- Replaced random initialization with **K-Means++**
- Added **CSV parser** with automatic header and label detection
- Implemented **Elbow Method** for optimal K selection
- Built **ASCII terminal visualizer** for cluster visualization

---

## 📈 K-Means++ vs Random Init (on Iris dataset)

| Method | Iterations |
|---|---|
| Random Init | 12 |
| K-Means++ | 8 |

**33% faster convergence** with smarter initialization.