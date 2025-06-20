# Online-Learning-Student-Drop-Out-Predictor
# 🎓 Student Dropout Risk Predictor

This machine learning project predicts whether a student is at risk of **dropping out** based on their behavioral, academic, and demographic data. It uses the **Open University Learning Analytics Dataset (OULAD)** and deploys a live web app via **Gradio**.

---

## 📌 Project Objective

> Identify students at risk of dropping out early using ML, so that institutions can intervene in time.

---

## 📁 Dataset

- 📦 **Source**: [Open University Learning Analytics Dataset (OULAD)](https://analyse.kmi.open.ac.uk/open_dataset)
- 📊 Data includes:
  - Student demographics (age, education, disability)
  - Course registration and dropout info
  - Virtual Learning Environment (VLE) engagement (clicks)
  - Assessment performance (grades)

---

## 📈 Features Used

| Feature              | Description                           |
|----------------------|---------------------------------------|
| `age_band`           | Age group (e.g. "0-35", "35-55")       |
| `highest_education`  | Highest education level attained       |
| `disability`         | Disability status (Y/N)               |
| `num_of_prev_attempts` | Number of previous module attempts |
| `studied_credits`    | Number of credits enrolled            |
| `total_clicks`       | Total interactions on the VLE         |
| `avg_score`          | Average assessment score              |


![image](https://github.com/user-attachments/assets/d0c0f2c1-0256-4bfc-b3ad-64d691000902)

---

## 🧠 Models Compared

| Model              | Accuracy | Recall (Dropouts) | ROC-AUC |
|-------------------|----------|-------------------|---------|
| Logistic Regression | 0.75    | 0.58              | 0.76    |
| Random Forest       | 0.78    | 0.60              | 0.79    |
| **XGBoost** (used)  | **0.79**| **0.61**          | **0.82** ✅ |

---

## ⚖️ Class Imbalance

- **69%** students continued (class 0)
- **31%** dropped out (class 1)
- Used `scale_pos_weight` and `class_weight='balanced'` to address imbalance
- ![image](https://github.com/user-attachments/assets/6acfc274-055a-456a-b597-a5add42c4fff)


---

## 🎮 Gradio App

![image](https://github.com/user-attachments/assets/46ff32c5-414b-452d-8a58-b5efb747042e)


> The web app takes user inputs (age, education, performance, etc.) and predicts if a student is likely to drop out.


---

## 🚀 How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/dropout-risk-predictor.git
cd dropout-risk-predictor

pip install pandas scikit-learn xgboost gradio

python app.py  # or run in a Jupyter/Colab notebook
