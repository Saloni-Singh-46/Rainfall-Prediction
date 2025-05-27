# 🌧️ Rainfall Prediction - Will it Rain Tomorrow?

This project aims to predict whether it will rain tomorrow using historical weather data from the [Australian weather dataset](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package). We use classification algorithms to build predictive models based on meteorological variables.

---

## 📂 Dataset

The dataset used is **weatherAUS.csv**, which contains daily weather observations from numerous Australian weather stations. The target variable is:

- `RainTomorrow`: whether it will rain the next day (`Yes` or `No`).

Other important features include:
- `Rainfall`, `Humidity9am`, `Humidity3pm`, `WindGustSpeed`, `Pressure9am`, `RainToday`, `Temp3pm`, etc.

---

## 🛠️ Project Workflow

### 1. **Data Preprocessing**
- Dropped columns with more than 30% missing values
- Imputed missing numeric values with the median
- Imputed missing categorical values with the mode
- Encoded categorical variables (`RainToday`, `RainTomorrow`, `WindDir`, etc.)
- Scaled numerical features using StandardScaler
- Handled class imbalance using undersampling
- Split dataset into 80% training and 20% testing sets

### 2. **Exploratory Data Analysis (EDA)**
- Identified top correlated features to `RainTomorrow`
- Visualized distributions and box plots for rainfall, humidity, and wind
- Explored seasonal and location-based rain trends
- Detected moderate class imbalance: ~22% Yes, ~78% No

### 3. **Modeling**
We trained the following classification algorithms:

- Logistic Regression
- Decision Tree
- Random Forest
- Support Vector Machine (SVM)
- XGBoost

### 4. **Model Evaluation**
Evaluated using:
- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC Curve

---

## 📊 Results

| Model               | Accuracy | Precision | Recall | F1 Score | ROC AUC |
|--------------------|----------|-----------|--------|----------|---------|
| Logistic Regression| 85.3%    | 74.8%     | 56.1%  | 64.1%    | 0.82    |
| Decision Tree      | 79.2%    | 64.5%     | 61.2%  | 62.8%    | 0.76    |
| Random Forest      | 87.9%    | 81.0%     | 62.7%  | 70.7%    | 0.85    |
| SVM (RBF Kernel)   | 86.1%    | 78.3%     | 57.9%  | 66.4%    | 0.83    |
| XGBoost            | **89.2%**| **83.4%** | **65.1%** | **73.1%** | **0.87** |

➡️ **XGBoost** outperformed other models across most metrics.

---

## 📁 File Structure
