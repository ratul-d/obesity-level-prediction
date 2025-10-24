# Predicting Obesity Levels Based on Eating Habits and Physical Condition

---

## Overview

This project applies data analytics and machine learning techniques to estimate obesity levels in individuals based on their eating habits and physical conditions. Using the *Estimation of Obesity Levels Based on Eating Habits and Physical Condition* dataset from the UCI Machine Learning Repository, the analysis explores lifestyle factors influencing obesity and builds predictive models to classify individuals into obesity categories.

---

## Objectives

* Perform exploratory data analysis to identify key factors correlated with obesity levels.
* Apply preprocessing techniques to handle categorical and numerical data.
* Train and evaluate classification models to predict obesity levels.
* Interpret model performance and feature importance to derive actionable insights.

---

## Dataset Description

**Source:** [UCI Machine Learning Repository – Estimation of Obesity Levels Based on Eating Habits and Physical Condition](https://doi.org/10.24432/C5H31Z)  
**Authors:** Fabio Mendoza Palechor, Alexis De la Hoz Manotas (2019)  
**License:** Creative Commons Attribution 4.0 International (CC BY 4.0)

**Key Facts:**

* **Instances:** 2,111
* **Features:** 16 (plus one target variable, `NObeyesdad`)
* **Target Classes:**

  * Insufficient Weight
  * Normal Weight
  * Overweight Level I
  * Overweight Level II
  * Obesity Type I
  * Obesity Type II
  * Obesity Type III

**Geographic Scope:** Mexico, Peru, and Colombia  
**Missing Values:** None

**Attribute Examples:**

* Demographic: `Gender`, `Age`
* Eating Habits: `FAVC` (High-caloric food frequency), `NCP` (Number of main meals)
* Physical Condition: `FAF` (Physical activity frequency), `TUE` (Technology usage time)
* Lifestyle: `SMOKE`, `CALC`, `MTRANS` (Transportation type)

---

## Project Structure

```
obesity-level-prediction/
├── data/
│   ├── raw/                       # Original dataset
│   └── processed/                 # Cleaned and feature-engineered data
│
├── jupyter_notebooks/             # Jupyter notebooks for analysis and modeling
├── models/                        # Trained model artifacts
│
├── results/
│   ├── accuracy_figures/          # Figures of model accuracies
│   ├── analysis_figures/          # Figures from analysis
│   └── metrics/                   # Model performance and comparison files
│
├── requirements.txt
└── README.md
```

---

## Methodology

1. **Exploratory Data Analysis (EDA)**

   * Statistical summaries and distribution analysis
   * Correlation heatmaps and categorical breakdowns
   * Visualization of obesity levels across demographic and lifestyle attributes

2. **Data Preprocessing**

   * Label encoding for categorical variables
   * Feature scaling of continuous variables
   * Splitting data into training and test sets

3. **Model Development**

   * Baseline models: Logistic Regression, Decision Tree, Random Forest
   * Hyperparameter tuning using GridSearchCV
   * Model evaluation via accuracy, precision, recall, F1-score, and confusion matrix

4. **Insights Extraction**

   * Identification of most influential features
   * Discussion of behavioral and lifestyle factors linked to higher obesity levels

---

## Results and Analysis

The predictive models developed for obesity classification were rigorously evaluated using multiple metrics, including accuracy, precision, recall, F1-score, and feature importance. The evaluation highlights model performance, robustness, and the influence of key lifestyle and demographic features.

### Model Performance Overview

<p align="center">
  <img src="results/accuracy_figures/Model%20Comparisons%20A.png" alt="Precision-Recall Curves" width="900">
</p>

Among all models, **Random Forest** demonstrated the best generalization performance, achieving **94.33% test accuracy** while effectively balancing predictive power and resistance to overfitting.



---

### Precision-Recall Analysis

The precision-recall curves provide a detailed view of model performance across all obesity categories, emphasizing the trade-offs between precision and recall for minority classes.

<p align="center">
  <img src="results/accuracy_figures/Precision-Recall%20Curves.png" alt="Precision-Recall Curves" width="600">
</p>

*Figure 1: Precision-Recall curves for all models, illustrating classification effectiveness across obesity categories.*

Analysis of these curves indicates that **Random Forest and Decision Tree models maintain high precision and recall across most classes**, while Naive Bayes struggles with class imbalance.

---

### Feature Importance Across Models

Feature importance analysis highlights the most influential variables in predicting obesity levels. Random Forest feature ranking shows that both demographic and lifestyle factors significantly contribute to model predictions.

![Feature Importance Across Models](results/accuracy_figures/Feature%20Importance%20Across%20Models.png)
*Figure 2: Feature importance scores across models.*

These insights align with domain knowledge, confirming that **sedentary habits, dietary patterns, and genetic predisposition** are strong determinants of obesity.

---

### Key Observations

* **Random Forest** consistently outperforms baseline models across multiple evaluation metrics.
* Features such as **weight, height, gender and age** are most predictive of obesity levels.
* Visualizations from exploratory data analysis indicate a clear trend between **sedentary lifestyle behaviors and higher obesity categories**, providing actionable insights for intervention strategies.

Overall, the combination of model performance metrics, precision-recall analysis, and feature importance evaluation provides a **comprehensive understanding of predictive factors** and highlights the robustness of ensemble methods like Random Forest for multi-class obesity classification.

---

## Technologies Used

* **Programming Language:** Python
* **Libraries:** pandas, numpy, matplotlib, seaborn, scikit-learn
* **Environment:** Jupyter Notebook

---

## How to Run

1. Clone this repository:

   ```bash
   git clone https://github.com/ratuld/obesity-level-prediction.git
   cd obesity-level-prediction
   ```
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```
3. Open and run the notebooks:

   ```bash
   jupyter notebook
   ```
4. Review outputs in the `/results` directory.

---

## Citation

If using the dataset, please cite:

> Estimation of Obesity Levels Based On Eating Habits and Physical Condition [Dataset]. (2019). UCI Machine Learning Repository. [https://doi.org/10.24432/C5H31Z](https://doi.org/10.24432/C5H31Z)

---