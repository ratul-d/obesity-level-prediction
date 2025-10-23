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
│   ├── raw/              # Original dataset
│   └── processed/        # Cleaned and feature-engineered data
│
├── notebooks/            # Jupyter notebooks for analysis and modeling
├── models/               # Trained model artifacts
│
├── results/
│   ├── accuracy_figures/          # Figures of model accuracies
│   ├── analysis_figures/          # Figures from analysis
│   └── metrics/          # Model performance and comparison files
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

## Results Summary

* Achieved **95%** classification accuracy using Random Forest.
* Age, weight, daily water intake (CH2O), eating between meals (CAEC), and family history of overweight were among the key factors associated with obesity.
* Visualization results show clear trends between sedentary habits and higher obesity categories.

### Model Performance Metrics

| Model                | Training Accuracy | Testing Accuracy | Notes |
|----------------------|------------------:|-----------------:|:------|
| Logistic Regression  | 0.8418 | 0.8274 | Baseline linear model |
| Naive Bayes          | 0.5806 | 0.6052 | Underfitting; assumes independence |
| Decision Tree        | 1.0000 | 0.9196 | Overfitting evident |
| Random Forest        | 1.0000 | 0.9433 | Best overall performance |
| KNN                  | 0.9117 | 0.8723 | Good balance of bias-variance |

Among all models, **Random Forest** achieved the best generalization performance, balancing predictive power and robustness against overfitting.

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