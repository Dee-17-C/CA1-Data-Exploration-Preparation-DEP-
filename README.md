# CA1: Data Exploration & Preparation (DEP) - Credit Card Defaults

**Institution:** CCT College Dublin  
**Course:** BSc (Hons) in Computing in IT (4th Year)  
**Student Name:** Daniel Adejare  
**Student ID:** 2026848  
**Lecturer:** Dr. Muhammad Iqbal  

---

## Project Overview
The global credit card industry faces significant financial risks due to customer defaults. Accurately predicting the probability of default is a critical challenge in the **Economy and Finance** domain. 

The motivation for this project is to explore historical credit card client data to identify demographic and behavioral risk factors (covariations and variations) associated with defaults. Furthermore, because handling high-dimensional financial tracking data is computationally expensive, this project cleans anomalies, applies feature engineering, and uses Principal Component Analysis (PCA) to reduce dimensionality without losing critical financial variance.

**Dataset Used:** "Default of Credit Card Clients" from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients).

---

## Research Questions
1. **(Variation)** How does the initial credit limit (`LIMIT_BAL`) vary between clients who default and those who do not?
2. **(Covariation)** Is there an unusual pattern or high correlation (redundancy) across the 6-month historical billing data (`BILL_AMT1` to `BILL_AMT6`)?
3. **(Variation)** How do demographic attributes like Education and Age vary between defaulters and non-defaulters, and how can they be transformed without introducing multicollinearity?
4. **(Covariation)** Can Principal Component Analysis (PCA) successfully compress the high-dimensional financial tracking data while retaining at least 90% of the critical variance?

---

## Methodology & Pipeline
1. **Data Cleaning:** 
   * Dropped redundant metadata/ID columns.
   * Handled undocumented, out-of-range categorical data in the `EDUCATION` and `MARRIAGE` features.
   * Removed extreme outliers in the credit limit column (>99th percentile).
2. **Exploratory Data Analysis (EDA):** 
   * Analyzed demographic distributions and generated correlation heatmaps to justify dimensionality reduction (billing amounts showed >0.80 correlation).
3. **Feature Engineering (Encoding):** 
   * Applied One-Hot Encoding to categorical variables (`SEX`, `EDUCATION`, `MARRIAGE`). Set `drop='first'` to avoid the dummy variable trap and multicollinearity.
4. **Dimensionality Reduction (PCA):** 
   * Standardized 12 continuous financial tracking features using `StandardScaler`.
   * Applied PCA to compress the features, successfully reducing the dimensions from 12 down to 6 while retaining **90.04%** of the cumulative variance.

---

## Repository Structure

```
CA1-Data-Exploration-Preparation-DEP-/
├── README.md
├── dataset/
│   └── default of credit card clients.xls
├── notebook/
│   └── CA1_Data_Exploration_&_Preparation_(DEP)_2026848.ipynb
├── outputs/
│   ├── visualization_1.png
│   ├── visualization_2.png
│   ├── visualization_3.png
│   ├── visualization_4.png
│   ├── visualization_5.png
│   └── visualization_6.png
└── poster/
    └── CA1_DATA_EXPLORATION_&_PREPARATION_CREDIT_CARD_DEFAULTS.pptx

```

---

## Technologies & Libraries Used
* **Python 3**
* **Pandas** (Data manipulation and cleaning)
* **NumPy** (Numerical operations)
* **Matplotlib & Seaborn** (Data visualization)
* **Scikit-Learn** (`StandardScaler`, `OneHotEncoder`, `PCA`)

---

## References
1. Yeh, I. C., & Lien, C. H. (2009). The comparisons of data mining techniques for the predictive accuracy of probability of default of credit card clients. *Expert Systems with Applications*, 36(2), 2473-2480.
2. UCI Machine Learning Repository. (2016). Default of Credit Card Clients Dataset.
