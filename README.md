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
  <img src="results/accuracy_figures/Model%20TRAIN-TEST%20Accuracies.png" alt="Model TRAIN-TEST Accuracies" width="550">
</p>

<p align="center">
  <img src="results/accuracy_figures/Model%20Comparisons%20A.png" alt="Model Comparisons A" width="900">
</p>

Among all models, **Random Forest** demonstrated the best generalization performance, achieving **~95% test accuracy** while effectively balancing predictive power and resistance to overfitting.


### Precision-Recall and ROC Curve Analysis

The **Precision-Recall (PR)** and **Receiver Operating Characteristic (ROC)** curves provide complementary perspectives on model performance across all obesity categories.

* The **Precision-Recall curves** emphasize the trade-off between precision (positive predictive value) and recall (sensitivity), which is especially informative for **imbalanced datasets** where certain obesity classes are underrepresented.
* The **ROC curves**, on the other hand, illustrate the relationship between the **True Positive Rate (TPR)** and **False Positive Rate (FPR)**, offering a broader view of overall classification performance.

<p align="center">
  <img src="results/accuracy_figures/Precision-Recall%20Curves.png" alt="Precision-Recall Curves" width="45%">
  <img src="results/accuracy_figures/ROC%20Curves.png" alt="ROC Curves" width="45%">
</p>

*Figure 1: Precision-Recall and ROC curves for all models.*

Analysis of these curves indicates that **Random Forest and Decision Tree models maintain strong performance**, demonstrating **high precision, recall, and AUC scores** across most obesity categories. In contrast, **Naive Bayes shows noticeable sensitivity to class imbalance**, resulting in reduced precision and recall for minority classes.


### Feature Importance Across Models

Feature importance analysis highlights the most influential variables in predicting obesity levels. Random Forest feature ranking shows that both demographic and lifestyle factors significantly contribute to model predictions.

![Feature Importance Across Models](results/accuracy_figures/Feature%20Importance%20Across%20Models.png)
*Figure 2: Feature importance scores across models.*

These insights align with domain knowledge, confirming that **sedentary habits, dietary patterns, and genetic predisposition** are strong determinants of obesity.


### Key Observations

* **Random Forest** consistently outperforms baseline models across multiple evaluation metrics.
* Features such as **weight, height, gender and age** are most predictive of obesity levels.
* Visualizations from exploratory data analysis indicate a clear trend between **sedentary lifestyle behaviors and higher obesity categories**, providing actionable insights for intervention strategies.

Overall, the combination of model performance metrics, precision-recall analysis, and feature importance evaluation provides a **comprehensive understanding of predictive factors** and highlights the robustness of ensemble methods like Random Forest for multi-class obesity classification.

---

## Further Model Improvements

To systematically enhance predictive performance beyond baseline models, an iterative modeling approach was adopted. Starting with **hyperparameter tuning** of the Random Forest (RF) model, the process progressively advanced through **boosting algorithms** and **ensemble integration techniques**, resulting in substantial gains in accuracy and generalization capability.


### 1. Hyperparameter Tuning

Using **GridSearchCV**, optimal hyperparameters were identified for the **Random Forest (RF)** model to improve predictive accuracy and control overfitting.
The tuning process explored multiple parameter categories, including:

* `n_estimators` – number of trees in the forest
* `max_depth` – maximum depth of each decision tree
* `min_samples_leaf` – minimum number of samples required at a leaf node
* `max_features` – fraction of features considered for each split
* `criterion` – function used to measure split quality
* `bootstrap` – whether bootstrap samples are used when building trees

This optimization **improved the model’s accuracy from 94.7% to 95.9%**, demonstrating the strong impact of parameter refinement on model stability and generalization.


### 2. Progressive Model Development

Following the optimized Random Forest, **boosting-based algorithms** — **XGBoost (95.7%)** and **LightGBM (96.6%)** — were introduced to further improve performance by leveraging gradient boosting and efficient leaf-wise learning.
These models achieved superior accuracy through enhanced gradient optimization and regularization mechanisms, outperforming traditional bagging approaches.

To capture the complementary strengths of these individual learners, **ensemble meta-learning** strategies were applied.
A **Stacking Classifier** (Logistic Regression as meta-model) achieved **96.6% accuracy**, integrating diverse model outputs for stronger generalization.
Finally, a **Voting Classifier** (soft voting) combined all tuned models, reaching the **highest overall accuracy of 96.9%**, marking the peak of performance improvement across all stages.


### 3. Model Performance Comparison (Post-Tuning)

<p align="center">
  <img src="results/accuracy_figures/Tuned%20Model%20Accuracies.png" alt="Tuned Model Accuracies" width="550">
</p>

<p align="center">
  <img src="results/accuracy_figures/Model%20Comparisons%20C.png" alt="Model Comparisons C" width="750">
</p>

### 4. Ensemble Insights

* **LightGBM** achieved **96.6% accuracy**, leveraging gradient-based one-side sampling and leaf-wise tree growth for efficient learning.
* **Stacking Classifier** (Logistic Regression meta-model) reached **96.6% accuracy**, confirming the synergy among base learners.
* **Voting Classifier** delivered the **highest accuracy (96.9%)**, demonstrating that blending diverse tuned models yields the most stable and reliable predictions.
* **Random Forest** and **XGBoost** achieved **95.9%** and **95.7%** accuracy respectively, providing a strong foundation for subsequent ensemble improvements.
* Overall, the progression from individual optimization to meta-ensemble integration substantially enhanced model robustness and performance across obesity categories.


### 5. Key Takeaways

* **Stepwise refinement** — from Random Forest tuning to boosting and ensemble integration — consistently improved model accuracy.
* **Boosting algorithms** such as **LightGBM** and **XGBoost** outperformed traditional ensembles, capturing complex multi-class patterns effectively.
* **Stacking and voting** strategies provided the final performance lift, ensuring strong generalization and stable multi-class classification.

---

## Technologies Used

* **Programming Language:** Python
* **Libraries:** pandas, numpy, matplotlib, seaborn, scikit-learn, scikit-learn-intelex, xgboost, lightgbm
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