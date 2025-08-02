# 🏠 Housing Price Prediction

## 📌 Objective
Build a machine learning model to predict housing prices using feature engineering, outlier detection, and model tuning.

---

## 📂 Dataset
- **Source:** [Kaggle](https://www.kaggle.com/)
- **Size:** ~20,000 records  
- **Features:**
  - **Categorical:** city, street, statezip, waterfront, view, condition, floors
  - **Numerical:** sqft_living, sqft_lot, sqft_above, sqft_basement, bedrooms, bathrooms, yr_built, yr_renovated
  - **Target:** price

---

## 🔍 Methodology

### 1. Exploratory Data Analysis (EDA)
- Plotted histograms and box plots to understand distributions.
- Removed extreme outliers in price.
- Checked correlation between features and target.

### 2. Feature Engineering
- `House_Age` = Current Year – yr_built  
- `Years_Since_Renovation` = Current Year – yr_renovated (0 if never renovated)  
- Applied **Target Encoding with smoothing** for categorical features (e.g., `city`).
- Dropped low-value columns (`street`, `statezip`).

### 3. Data Preprocessing
- Handled missing values.
- Scaled numerical features.
- Removed price outliers for better model training.

### 4. Model Development
- Baseline models (Linear Regression, Random Forest) performed poorly (**R² < 0.10**).
- Switched to **XGBoost Regressor**, tuned hyperparameters.
- Applied **k-fold cross-validation** for robust validation.

---

## 📊 Results
- **Final Model:** XGBoost Regressor
- **R²:** 0.72  
- **MAE:** 76,404  
- **RMSE:** 106,585  

### Feature Importance
| Rank | Feature        | Importance |
|------|---------------|------------|
| 1    | sqft_living    | 26.6%      |
| 2    | city          | 26.3%      |
| 3    | sqft_above    | 9.4%       |
| 4    | view          | 6.1%       |
| 5    | waterfront    | 5.0%       |

---

## ✅ Key Learnings
- Improved model from **R² < 0.10** to **R² = 0.72** through:
  - Outlier detection and removal
  - Feature engineering
  - Target encoding with smoothing
  - Model tuning and cross-validation

---

## 🛠 Tools & Technologies
- **Python**: Pandas, NumPy, Scikit-learn, XGBoost, Category Encoders
- **Visualization**: Matplotlib, Seaborn
- **Jupyter Notebook** for development
- **GitHub** for version control and project showcase

---

## 📈 Future Improvements
- Experiment with advanced feature selection
- Use stacking or ensemble models
- Include geospatial analysis for location-based insights

---
