# 🌌 Stellar Classification: Star, Galaxy, or Quasar?

![Python](https://img.shields.io/badge/Python-3.9-blue) ![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-orange) ![Accuracy](https://img.shields.io/badge/Model%20Accuracy-97.6%25-green)

### 🔭 The Mission
The universe is massive. Astronomers capture millions of images of the sky, but manually checking every single dot of light is impossible.

I built a Machine Learning system to automate this process. Using spectral data from the **Sloan Digital Sky Survey (SDSS)**, this tool automatically classifies celestial objects into one of three categories:
1.  **🌟 STAR:** A self-luminous celestial body.
2.  **🌌 GALAXY:** A massive system of stars, gas, and dark matter.
3.  **⚫ QSO (Quasar):** An extremely luminous active galactic nucleus (the hardest to detect!).

---

### 📊 The Results at a Glance
I trained and benchmarked 5 different algorithms. **Random Forest** emerged as the champion, achieving near-perfect accuracy on Stars and Galaxies.

| Model | Overall Accuracy | Quasar (QSO) Detection |
| :--- | :--- | :--- |
| **Random Forest** | **97.6%** 🏆 | **Precision: 94%** |
| Decision Tree | 97.1% | Precision: 80% |
| SVM (Tuned) | 95.5% | Precision: 83% |
| Logistic Regression | 95.5% | Precision: 89% |
| SGD Classifier | 91.2% | Precision: 74% |

> *Key Insight: Quasars are often mistaken for Stars because they are point-sources of light. My Random Forest model successfully distinguished them with a high F1-score of 0.89.*

---

### 🛠️ How I Built It (Methodology)

#### 1. Data Cleaning & Feature Engineering
The raw dataset contained 100,000 observations with 17 features.
* **Outlier Removal:** Used the Interquartile Range (IQR) method to remove noisy data points, retaining 90,632 clean records for training.
* **Feature Selection:** I hypothesized that ID columns (like `run_ID`, `cam_col`, `plate`) were noise. I ran tests removing them and found model accuracy remained stable, proving these features were unnecessary.
* **Balancing:** The dataset was heavily skewed (mostly Galaxies). I used `class_weight='balanced'` in my models to ensure Quasars weren't ignored.


#### 2. Technologies Used
* **Language:** Python
* **Libraries:** Pandas, NumPy (Data Manipulation), Matplotlib, Seaborn (Visualization)
* **ML Framework:** Scikit-Learn (GridSearchCV, RandomForest, SVM, SGD)

---

### 👨‍💻 About the Author
**Karthik Kunnamkumarath**
*Aerospace Engineer | Project Management Professional (PMP) | AI Solutions Developer*

I combine engineering precision with data science to solve complex problems.
* 📍 Toronto, ON
* 💼 [LinkedIn Profile](https://linkedin.com/in/4karthik95)
* 📧 Aero13027@gmail.com
