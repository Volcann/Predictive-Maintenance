# Project Title: Predictive Modeling for Machine Failure

## Repository Description

This repository contains a comprehensive analysis and predictive modeling project utilizing a dataset focused on [briefly describe the dataset, e.g., machine failure]. The project encompasses data preprocessing, exploratory data analysis (EDA), feature selection, model training, evaluation, and interpretation of results.

### Project Overview

The objective of this project is to build a predictive model that accurately classifies Target variable weather machine failed or not failed. The analysis follows a systematic approach to ensure robustness and reliability in predictions.

### Key Steps:

1. **Data Acquisition**:
   - The dataset is sourced from [Machine Predictive Maintance Classification](https://www.kaggle.com/datasets/shivamb/machine-predictive-maintenance-classification/code?datasetId=1697740), containing 10000 observations and 14 features, including `Air temperature [K]`, `Process temperature [K]`, `Rotational speed [rpm]`, `Torque [Nm]`, `Tool wear [min]`, `Target`, `Failure Type`.

2. **Data Preprocessing**:
   - Handled missing values and outliers.
   - Conducted data cleaning and normalization.
   - Utilized scaling techniques to prepare the data for model training.

3. **Exploratory Data Analysis (EDA)**:
   - Visualized distributions and relationships among features.
   - Identified potential correlations and patterns that inform feature selection.

4. **Feature Selection**:
   - Employed `SelectKBest` with the chi-squared test to evaluate feature importance.
   - Focused on key features such as **Tool wear [min]**, **Torque [Nm]**, and **Rotational speed [rpm]**, which demonstrated strong predictive capabilities.

5. **Model Selection and Training**:
   - Trained Random Forest.
   - Evaluated models based on accuracy, precision, recall, F1-score, and confusion matrix analysis.

6. **Results**:
   - The best-performing model achieved an accuracy of **98.50%**.
   - Classification report metrics indicate strong performance for class 0 but highlight the need for improvement in class 1 predictions.

7. **Model Interpretation**:
   - Analyzed feature importance scores to interpret model predictions.
   - Investigated the impact of key features on model outputs, providing insights into the decision-making process of the model.

8. **Conclusion**:
   - The project demonstrates effective data analysis and modeling strategies, with implications for improving predictions, particularly for the minority class.
   - Recommendations for future work include exploring more advanced modeling techniques and rebalancing strategies to enhance detection of the minority class.

### Installation and Usage
To run the analysis and models, clone the repository and follow the instructions in the `README.md` file.

```bash
git clone [https://github.com/Volcann/Predictive-Maintenance.git]
cd [project directory]
```

### Technologies Used
- Python
- Libraries: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`, etc.
