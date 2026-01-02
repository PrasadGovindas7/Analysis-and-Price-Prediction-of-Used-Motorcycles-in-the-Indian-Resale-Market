# 🚲 Analysis and Price Prediction of Used Motorcycles in the Indian Resale Market

## 📌 Project Overview

The Indian used motorcycle market is influenced by several factors such as vehicle age, usage, engine specifications, brand reputation, ownership history, and geographic location. Accurately estimating resale prices is challenging due to inconsistent pricing and heterogeneous listings.

This project performs an end-to-end **data analysis and machine learning workflow** to identify the key factors affecting used motorcycle resale prices and to build a reliable, interpretable regression model for price prediction.

---

## 🎯 Objectives

* Understand the major drivers of used motorcycle resale prices
* Perform comprehensive data cleaning on real-world, messy data
* Conduct Exploratory Data Analysis (EDA) to uncover pricing patterns
* Engineer meaningful features for modeling
* Build and evaluate a regression-based price prediction model
* Validate model assumptions using residual diagnostics

---

## 📂 Dataset Description

* **Records:** ~7,800 raw listings (≈5,800 after cleaning)
* **Features:** Motorcycle specifications, ownership details, location, and resale price
* **Target Variable:** `price` (INR), later transformed to `log_price`

### Key Raw Features

* `model_name`
* `model_year`
* `kms_driven`
* `mileage`
* `power`
* `owner`
* `location`
* `price`

---

## 🛠️ Data Cleaning & Preprocessing

Real-world inconsistencies were addressed, including:

* Converting text-based numeric fields (kms driven, mileage, power) into numeric format
* Handling missing values and semantically incorrect entries
* Removing invalid price values
* Detecting and treating outliers using IQR-based analysis
* Applying **log transformation** to stabilize price variance
* Extracting brand names from model names
* Encoding categorical variables and scaling numerical features using pipelines

---

## 📊 Exploratory Data Analysis (EDA)

EDA revealed:

* Strong positive influence of **model year** and **engine power** on resale price
* Clear depreciation effect with increasing **kilometers driven**
* Significant impact of **brand**, **owner type**, and **location**
* Highly right-skewed price distribution, corrected via log transformation

Visualizations included:

* Scatter plots (price vs numerical features)
* Boxplots for categorical variables
* Correlation heatmap
* Geographic distribution of listings (city-level)

---

## 🤖 Modeling Approach

* **Model Used:** Linear Regression
* **Why Linear Regression?**

  * Clear linear relationships after transformation
  * Strong interpretability
  * Stable generalization performance

### Data Splitting

* Train – Validation – Test split
* Ensured unbiased performance evaluation and overfitting checks

### Evaluation Metrics

* **R² (Coefficient of Determination)**
* **RMSE (Root Mean Squared Error)**

---

## 📈 Model Performance

* **R² Score:** ~0.85–0.87 across train, validation, and test sets
* **RMSE:** Stable across all splits
* No evidence of overfitting
* Regularization (L1/L2) was evaluated but found unnecessary

---

## 🔍 Residual Diagnostics

To validate regression assumptions, the following diagnostics were performed:

* Residuals vs Fitted Values
* Histogram of Residuals
* Q–Q Plot
* Scale–Location Plot

**Conclusion:**
Residual diagnostics confirmed that linear regression assumptions were reasonably satisfied after log transformation, validating the suitability of the model.

---

## 🧠 Key Insights

* Newer motorcycles retain significantly higher resale value
* Higher engine power commands a price premium
* Increased usage (kms driven) leads to predictable depreciation
* Brand reputation strongly affects resale pricing
* First-owner bikes sell at higher prices
* Metro cities exhibit higher resale prices and variability

---

## ⚠️ Limitations

* No listing or transaction date (temporal pricing effects not modeled)
* City-level location data used as a proxy for regional demand
* Listings represent advertised prices, not confirmed sales

---

## 🏁 Conclusion

This project demonstrates a complete, disciplined machine learning workflow—from raw data inspection to model validation—while prioritizing interpretability and real-world applicability.

---

## 🧩 Tools & Technologies

* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* Scikit-learn

---

## 📌 Author

**Prasad Govindas**
*Data Science & Analytics Enthusiast*

---

⭐ *If you found this project useful, feel free to star the repository!*
