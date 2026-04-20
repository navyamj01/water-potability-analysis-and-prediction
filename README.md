# 💧 Water Potability Analysis & Prediction

This project focuses on analyzing water quality parameters and building machine learning models to predict whether water is safe for drinking (potable) or not.

---

## 📊 Problem Statement

Given various physicochemical properties of water, the goal is to:

- Predict whether water is **potable (1)** or **non-potable (0)**
- Understand the **factors affecting water quality**
- Evaluate model performance and limitations

---

## 📁 Dataset

The dataset contains the following features:

- pH  
- Hardness  
- Solids (Total Dissolved Solids)  
- Chloramines  
- Sulfate  
- Conductivity  
- Organic Carbon  
- Trihalomethanes  
- Turbidity  

**Target Variable:**
- `Potability` (1 = Safe, 0 = Not Safe)

---

## ⚙️ Workflow

### 1. Data Preprocessing
- Handled missing values using **median imputation**
- Applied **feature scaling** (for Logistic Regression)
- Created clean train/test datasets

---

### 2. Exploratory Data Analysis (EDA)
- Checked feature distributions
- Analyzed correlations
- Observed overlapping feature ranges between classes

---

### 3. Model Training

#### 📌 Logistic Regression
- Applied using a preprocessing pipeline
- Used `class_weight='balanced'` to handle class imbalance

**Observations:**
- Initial predictions were biased toward majority class
- After balancing, predictions improved
- However, model showed **underfitting**

---

#### 📌 Random Forest
- Used as a more advanced, non-linear model
- Tuned parameters:
  - `n_estimators=200`
  - `max_depth=10`
  - `min_samples_split=5`

**Observations:**
- Slight improvement over Logistic Regression
- Still struggled with class separation
- Performance limited by dataset characteristics

---

## 📈 Model Evaluation

Metrics used:
- Accuracy  
- Precision  
- Recall  
- F1 Score  
- Log Loss  
- ROC-AUC  

---

### 🔍 Key Results

| Model                | Log Loss | ROC-AUC |
|---------------------|--------|--------|
| Logistic Regression | ~0.69  | ~0.65  |
| Random Forest       | ~0.60  | ~0.68  |

---

## 🧠 Key Insights

- Logistic Regression produced probabilities close to **0.5**, indicating weak learning
- Random Forest captured more complexity but **did not significantly improve performance**
- Feature overlap between classes makes classification difficult
- Model performance is **limited by data quality and separability**, not just model choice

---

## ⚠️ Challenges

- Moderate class imbalance
- High overlap between potable and non-potable samples
- Weak feature separability
- Underfitting in simpler models

---

## 🎯 Conclusion

- Logistic Regression was **not suitable** due to its inability to capture non-linear relationships
- Random Forest performed better but still showed limitations
- The dataset likely lacks strong predictive signals, making classification inherently difficult

---

## 🚀 Future Improvements

- Feature engineering (create new meaningful features)
- Try advanced models (XGBoost, Gradient Boosting)
- Apply SHAP for better interpretability
- Build a Streamlit app for user interaction

---

## 🛠️ Tech Stack

- Python  
- pandas, numpy  
- matplotlib, seaborn  
- scikit-learn  

---

## 📌 Project Status

✔ Data preprocessing completed  
✔ Model training & evaluation completed  
✔ Insights derived  
🔜 Model explainability (SHAP)  

---

## 🙌 Author

**Lakshay Kumar**

---

## ⭐ If you found this useful

Give this repo a ⭐ and feel free to fork!
