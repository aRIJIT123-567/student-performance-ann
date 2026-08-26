# 🎓 Student Performance Prediction — ANN

Predicting a student's final grade using an Artificial Neural Network (ANN), based on academic history, study habits, family background, and lifestyle factors.

<p align="center">
<img src="https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white" height="30">
<img src="https://img.shields.io/badge/TensorFlow-2.x-orange?logo=tensorflow&logoColor=white" height="30">
<img src="https://img.shields.io/badge/Keras-Deep%20Learning-red?logo=keras&logoColor=white" height="30">
<img src="https://img.shields.io/badge/scikit--learn-ML%20Utils-f7931e?logo=scikitlearn&logoColor=white" height="30">
<img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white" height="30">
<img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white" height="30">
<img src="https://img.shields.io/badge/License-MIT-green.svg" height="30">
<img src="https://img.shields.io/badge/Status-Work%20in%20Progress-yellow" height="30">
</p>

---

## 📌 Overview

This project builds a simple feed-forward Artificial Neural Network (ANN) to predict a student's **final grade (G3, 0–20 scale)** in a Math course, using features like study time, past failures, parental education, absences, and social habits.

It's designed as a **beginner-friendly deep learning project** covering the full ML pipeline: data loading, EDA, preprocessing, model building, training, evaluation, and visualization.

> 🚧 **Status: Work in Progress.** This repo currently contains the project plan, dataset, and folder structure. Notebook development and results are in progress — see the [Roadmap](#-roadmap) below.

---

## 📂 Dataset

- **Source:** [UCI Machine Learning Repository — Student Performance Data Set](https://archive.ics.uci.edu/dataset/320/student+performance)
- **File used:** `student-mat.csv` (Math course)
- **Size:** 395 students × 33 attributes
- **Target variable:** `G3` — final grade (0–20)

**Key features:**
| Feature | Description |
|---|---|
| `G1`, `G2` | Grades from period 1 and 2 |
| `studytime` | Weekly study time |
| `failures` | Number of past class failures |
| `absences` | Number of school absences |
| `Medu`, `Fedu` | Mother's / Father's education level |
| `goout`, `Dalc`, `Walc` | Social outings, weekday/weekend alcohol use |
| `schoolsup`, `famsup` | Extra educational/family support |

Full attribute list is documented in the notebook and on the [UCI dataset page](https://archive.ics.uci.edu/dataset/320/student+performance).

---

## 📁 Folder Structure

```
student-performance-ann/
│
├── data/
│   ├── raw/                          # original dataset (untouched)
│   └── processed/                    # cleaned/encoded data
│
├── notebooks/
│   └── Student_Performance_ANN.ipynb # main notebook
│
├── src/                              # optional: scripts for production-style code
│   ├── data_preprocessing.py
│   ├── model.py
│   ├── train.py
│   └── evaluate.py
│
├── models/
│   └── ann_model.h5                  # saved trained model
│
├── plots/
│   ├── loss_curve.png
│   └── predicted_vs_actual.png
│
├── requirements.txt
└── README.md
```

---

## 🧠 Planned Model Architecture

A simple fully-connected ANN built with Keras:

```
Input Layer      → number of features (after one-hot encoding)
Dense (64, ReLU)
Dropout (0.2)
Dense (32, ReLU)
Dense (1, linear)  → predicted G3
```

- **Loss:** Mean Squared Error (MSE)
- **Optimizer:** Adam
- **Metric:** Mean Absolute Error (MAE)
- **Regularization:** Dropout + Early Stopping (on validation loss)

---

## ⚙️ Installation & Usage

1. **Clone the repo**
   ```bash
   git clone https://github.com/<your-username>/student-performance-ann.git
   cd student-performance-ann
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the notebook**
   ```bash
   jupyter notebook notebooks/Student_Performance_ANN.ipynb
   ```
   Or open it directly in **Google Colab** — the notebook will download the dataset automatically, no manual setup needed.

---

## 🗺️ Roadmap

- [x] Set up project structure
- [x] Source and document dataset
- [ ] Exploratory Data Analysis (EDA)
- [ ] Data preprocessing (encoding, scaling, train/test split)
- [ ] Build ANN model
- [ ] Train and tune model
- [ ] Evaluate model (MAE, RMSE, R²)
- [ ] Visualize results (loss curves, predicted vs actual)
- [ ] Write up final results in this README

---

## 🚀 Stretch Goals (after v1 is complete)

- [ ] Drop `G1`/`G2` and re-train on demographic/behavioral features only
- [ ] Convert to a classification problem (pass/fail, `G3 ≥ 10`)
- [ ] Hyperparameter tuning (layers, neurons, dropout, learning rate)
- [ ] Compare ANN vs. Linear Regression / Random Forest baselines
- [ ] Feature importance with SHAP

---

## 🛠️ Tech Stack

- Python
- TensorFlow / Keras
- scikit-learn
- Pandas, NumPy
- Matplotlib, Seaborn

---

## 📄 License

This project is licensed under the MIT License — free to use, modify, and share.

---

## 🙏 Acknowledgements

- Dataset: Cortez, P., & Silva, A. (2008). *Using Data Mining to Predict Secondary School Student Performance*. UCI Machine Learning Repository.
