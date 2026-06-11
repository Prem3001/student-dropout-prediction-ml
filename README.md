# Machine Learning Approach for Student Dropout Prediction

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-v1.0+-orange.svg)
![Pandas](https://img.shields.io/badge/pandas-v2.0+-navy.svg)
![Matplotlib](https://img.shields.io/badge/matplotlib-3.5+-green.svg)

## 📌 Project Overview
Student attrition and dropout rates pose significant challenges to academic institutions globally. This project leverages the **UCI Student Dropout Dataset** to build an early-warning system capable of predicting whether a student will **Dropout, Graduate, or Remain Enrolled**. 

The core of this research is a rigorous statistical comparison between two classification techniques: **Multinomial Logistic Regression** (optimized via hyperparameter tuning) and **Linear Discriminant Analysis (LDA)**. The objective is to evaluate their trade-offs regarding predictive precision, structural interpretability, and computational overhead, while uncovering the foundational socioeconomic and academic indicators of institutional risk.

---

## 📊 Core Objectives & Methodology

* **Multi-Class Classification:** Isolate and predict 3 explicit student pathways (Graduate, Dropout, Enrolled).
* **Comparative Evaluation:** Match Multinomial Logit's probabilistic gradient optimization against LDA's dimensionality reduction/class-variance maximization.
* **Feature Importance Identification:** Pinpoint exactly which variables (e.g., second-semester performance, tuition status, demographics) act as the strongest early indicators of student attrition.

---

## 📈 Performance & Key Findings

### Statistical vs. Computational Benchmarks

| Metric | Multinomial Logistic Regression | Linear Discriminant Analysis (LDA) | Winner |
| :--- | :---: | :---: | :---: |
| **Mean CV Accuracy** | **76.52%** (± 0.017) | 75.84% (± 0.013) | **Logistic Regression** |
| **Weighted F1-Score**| **0.75** | 0.75 | **Tie** |
| **Log Loss (↓ lower)** | **0.5846** | 0.6409 | **Logistic Regression** |
| **ROC-AUC (OvR)** | **0.8779** | 0.8696 | **Logistic Regression** |
| **Training Time** | 0.0551 seconds | **0.0125 seconds** | **LDA (4.4x Faster)** |

### Class-Wise Performance (F1-Score)
* **Graduate:** Logistic Regression (**0.86**) vs. LDA (0.85)
* **Dropout:** Logistic Regression (**0.78**) vs. LDA (0.77)
* **Enrolled:** LDA (**0.44**) vs. Logistic Regression (0.41)

### Major Insights
1. **Academic Performance Wins:** Statistical coefficient matrices reveal that a student's **second-semester academic progress** (curricular units approved and grades) is the single most vital factor impacting retention.
2. **The Trade-Off:** **Logistic Regression** provides slightly tighter probability calibrations and overall better predictive capabilities for critical dropout interventions. However, **LDA** runs over **4x faster**, offering incredible computational efficiency and data scalability.

---

## 📁 Repository Structure
```text
├── Data/
│   └── student_dropout_dataset.csv   # UCI Repository student tracking data
├── Notebooks/
│   └── Student_Dropout_ML.ipynb     # Data fetching, model optimization, and evaluation pipelines
├── Presentations/
│   └── Project_Presentation.pptx     # Summary slides showcasing research methodologies
├── Requirements.txt                 # Dependencies required to reproduce the environment
└── README.md
