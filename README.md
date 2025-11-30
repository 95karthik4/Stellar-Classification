# 🌌 Stellar Classification using SDSS Data

![Python](https://img.shields.io/badge/Python-3.9-blue) ![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange) ![Random Forest](https://img.shields.io/badge/Best%20Model-Random%20Forest-green) ![Status](https://img.shields.io/badge/Status-Completed-success)

### 🔭 Project Overview
The Sloan Digital Sky Survey (SDSS) has mapped over one-third of the sky, producing a massive catalog of celestial data. This project leverages Machine Learning to automate the classification of these objects based on their spectral characteristics.

The goal was to build a classifier capable of accurately distinguishing between:
* **🌟 STAR:** Self-luminous celestial bodies.
* **🌌 GALAXY:** Massive systems of stars, gas, and dark matter.
* **⚫ QSO (Quasar):** Active galactic nuclei, which are notoriously difficult to distinguish from stars due to their point-like appearance.

---

### ⚙️ Data & Methodology

#### 1. The Dataset
* **Source:** SDSS Data Release 17 (100,000 observations).
* **Key Features Used:** * `u, g, r, i, z`: Photometric filters measuring brightness at different wavelengths.
    * `redshift`: A measure of the object's distance and speed.
    * `alpha`, `delta`: Celestial coordinates.

#### 2. Data Preprocessing
* [cite_start]**Outlier Detection:** Applied the **Interquartile Range (IQR)** method to filter out noise, reducing the dataset from 100,000 to ~90,632 high-quality records[cite: 25].
* **Feature Selection:** Conducted hypothesis testing to confirm that metadata columns (like `run_ID`, `cam_col`, `plate`) held no predictive power. [cite_start]Removing them improved training speed without sacrificing accuracy[cite: 440].
* **Handling Imbalance:** The dataset was heavily skewed towards Galaxies. [cite_start]We utilized **Class Weight Balancing** (`class_weight='balanced'`) to ensure the minority class (Quasars) was detected effectively[cite: 360].

#### 3. Model Development
We trained and hyper-tuned five different algorithms to find the optimal solution:
* Logistic Regression (Multinomial)
* Decision Tree Classifier
* **Random Forest Classifier (Winner)**
* Stochastic Gradient Descent (SGD)
* Support Vector Machine (SVM) with RBF Kernel

---

### 🏆 The Results: Why Random Forest Won
After rigorous GridSearch cross-validation, the **Random Forest** model outperformed all others. It successfully captured the complex non-linear relationships between spectral features.

**Optimal Hyperparameters found:**
* `n_estimators`: 200
* `max_depth`: 20
* `min_samples_split`: 2

#### Comparative Performance Table
| Model | Accuracy | QSO (Quasar) Precision | QSO Recall |
| :--- | :--- | :--- | :--- |
| **Random Forest** | **97.6%** | **0.94** | **0.85** |
| Decision Tree | 97.1% | 0.80 | 0.89 |
| SVM (RBF Kernel) | 95.5% | 0.83 | 0.91 |
| Logistic Regression | 95.5% | 0.89 | 0.77 |
| SGD Classifier | 91.2% | 0.74 | 0.86 |

#### Key Insights
* **Star Classification:** All models performed exceptionally well on Stars, achieving near 100% precision.
* **The Quasar Challenge:** Linear models (like Logistic Regression) struggled to distinguish Quasars from Galaxies. [cite_start]The Random Forest model achieved the best balance (F1-Score of 0.89), proving that ensemble methods are superior for this type of high-dimensional spectral data[cite: 488].

---

### 👥 The Team (Group 4)
This project was a collaborative effort.
* **Karthik Kunnamkumarath** (Logistic Regression, Analysis & Reporting)
* **Aswin Anil Bindu**
* **Danylo Gula**
* **Daria Ignateva**
* **Elizaveta Khoroshilova**
* **Jessica Bowmaster**

---

### 👨‍💻 Portfolio Owner
**Karthik Kunnamkumarath**
*Aerospace Engineer | Project Management Professional (PMP) | AI Solutions Developer*

I combine engineering precision with data science to solve complex problems.
* 📍 Toronto, ON
* 💼 [LinkedIn Profile](https://linkedin.com/in/4karthik95)
* 📧 Aero13027@gmail.com
