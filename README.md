# 🧹 Task 1: Data Cleaning & Preprocessing – AI/ML Internship

This task is part of my 30-day AI & ML internship focused on building foundational skills in preparing real-world datasets for machine learning. In this task, I performed essential data preprocessing techniques on a heart disease dataset.

---

## 📂 Dataset Overview

- **Dataset Name**: Heart Disease Prediction Dataset (Kaggle)
- **Features Used**: Includes both **numerical** and **categorical** features like:
  - Age, Cholesterol, Resting Blood Pressure, Max Heart Rate, Oldpeak
  - Chest Pain Type, ST Segment Slope, Resting ECG, Exercise Angina, Sex

---

## 🛠️ Tools & Libraries Used

- **Language**: Python
- **Libraries**:
  - `pandas` – data handling
  - `numpy` – numerical operations
  - `matplotlib`, `seaborn` – data visualization
  - `sklearn.preprocessing` – encoding & scaling

---

## 📊 Data Preprocessing Steps

### 1. **Missing Value Handling**
- Checked all columns using `.isnull().sum()`
- No missing values were present in the dataset.

### 2. **Outlier Detection & Handling**
- Created **boxplots** for all numerical columns to visualize outliers.
- Applied domain knowledge (especially for heart-related indicators):
  - `RestingBP`: Removed 0s (invalid BP) and capped at 200.
  - `Cholesterol`: Capped at 400 to remove biologically implausible values.
  - `MaxHR`: Removed values outside 60–110% of expected `(220 - age)` range.
  - `Oldpeak`: Capped at 6, as extremely high ST depression is rare.

### 3. **Categorical Encoding**
- **Sex**: Binary mapped (`M` → 1, `F` → 0)
- **ChestPainType**: One-hot encoded with `NAP` as base
- **RestingECG**: One-hot encoded with `Normal` as base
- **ExerciseAngina**: Binary mapped (`Y` → 1, `N` → 0)
- **ST_Slope**: Ordinal encoded based on clinical severity:
  - `Up` = 0, `Flat` = 1, `Down` = 2

### 4. **Feature Scaling**
- Applied **Standardization (Z-score)** to numerical columns:
  - `Age`, `RestingBP`, `Cholesterol`, `MaxHR`, `Oldpeak`

### 5. **Distribution Visualization**
- Plotted **KDE plots** for each numerical column to check distribution and effect of scaling.

---

## 🔍 Key Insights

- Many features in medical datasets have **clinical limits** that are more meaningful than purely statistical outliers.
- Some columns like `MaxHR` and `Oldpeak` benefit significantly from **domain-informed capping** rather than simple IQR-based filtering.
- Encoding and scaling greatly improve the readiness of the dataset for any downstream ML task.

---

## 📚 Learnings

- How to combine **domain knowledge** with preprocessing decisions
- Hands-on practice with:
  - One-hot and ordinal encoding
  - Outlier visualization and treatment
  - Standardization of features
- Importance of **clean, scaled, and encoded data** before applying ML algorithms

---

## 📎 Deliverables

- `Data cleaning and Preprocessing.ipynb` – Jupyter notebook with all code
- `README.md` – Task documentation
- `cleaned_and_processed_data.csv` – Cleaned and preprocessed dataset
- `heart.csv` - Raw data (from Kaggle)

---


---

