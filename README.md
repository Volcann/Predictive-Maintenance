# Predictive Maintenance 

## Overview

### What is Predictive Maintenance and Its Importance?

Predictive maintenance utilizes data analytics to forecast potential equipment failures, allowing for timely repairs before breakdowns occur. This proactive approach minimizes unplanned downtime, reduces maintenance costs, and extends the lifespan of machinery.

### How to Implement Predictive Maintenance

Implementing predictive maintenance effectively requires a thorough understanding of the machinery in question and the available sensor technologies. Proficiency in interpreting sensor data is essential to identify patterns that may indicate potential failures.

1. **Understanding Machine Operations**: A deep comprehension of the mechanics and functionalities of machinery is critical. Familiarity with operational parameters—such as temperature, pressure, power consumption, and vibration—is essential for assessing machine health.

2. **Failure Modes and Effects Analysis (FMEA)**: FMEA prioritizes maintenance activities by identifying potential failure points in a system, assessing their impact, and ranking them based on severity, frequency, and detectability. This ensures that maintenance efforts are directed toward high-risk areas, effectively preventing costly downtime and equipment damage.

3. **Predictive Analytics Methods**: Knowledge of machine learning and artificial intelligence is invaluable for constructing models that analyze historical data to predict future equipment failures.

### Effective Predictive Maintenance Strategy

An effective predictive maintenance strategy involves understanding various maintenance approaches—such as condition-based, time-based, and predictive maintenance. This knowledge assists in selecting the optimal strategy for diverse scenarios, ensuring efficient allocation of resources.

Industry-specific expertise is also crucial. Grasping the unique needs and challenges of different sectors—such as manufacturing, transportation, or energy—can significantly enhance predictive maintenance planning and execution.

In conclusion, effective predictive maintenance relies on a combination of technical knowledge, analytical skills, and industry-specific insights. This expertise enables the optimization of maintenance schedules, reduction of downtime, and enhancement of overall machinery reliability.

---

## Machine Predictive Maintenance Classification Dataset

Given the difficulty in obtaining and publishing real predictive maintenance datasets, we present a synthetic dataset designed to reflect authentic predictive maintenance scenarios encountered in the industry.

### Dataset Overview

- **Size**: 10,000 data points with 14 features.

| Feature                  | Description |
|--------------------------|-------------|
| UID                      | Unique identifier ranging from 1 to 10,000. |
| productID                | Letter L, M, or H for low (50% of products), medium (30%), and high (20%) quality variants, including a variant-specific serial number. |
| air temperature [K]      | Generated using a random walk process, normalized to a standard deviation of 2 K around 300 K. |
| process temperature [K]  | Generated using a random walk process, normalized to a standard deviation of 1 K, added to the air temperature plus 10 K. |
| rotational speed [rpm]   | Calculated from a power of 2860 W, overlaid with normally distributed noise. |
| torque [Nm]             | Normally distributed around 40 Nm with σ = 10 Nm (no negative values). |
| tool wear [min]         | The quality variants add 5/3/2 minutes of tool wear for H/M/L, respectively. |
| machine failure          | Label indicating whether the machine has failed for any of the failure modes. |

### Important Note

There are two target variables:
- **Target**: Failure or Not
- **Failure Type**: Type of Failure

**Caution**: Avoid using one of the targets as a feature to prevent data leakage.

---

## Key Insights

- **Air Temperature [K]**: Mean = 300.00 K; Range: 295.3 K to 304.5 K; Standard Deviation = 2.0 K.
- **Process Temperature [K]**: Mean = 310.01 K; Range: 305.7 K to 313.8 K; Standard Deviation = 1.48 K.
- **Rotational Speed [rpm]**: Mean = 1538.78 rpm; Range: 1168 rpm to 2886 rpm; Standard Deviation = 179.28 rpm.
- **Torque [Nm]**: Mean = 39.99 Nm; Range: 3.8 Nm to 76.6 Nm; Standard Deviation = 9.97 Nm.
- **Tool Wear [min]**: Mean = 107.95 minutes; Range: 0 to 253 minutes; Standard Deviation = 63.65 minutes.
- **Target Variable**: Heavily skewed towards 0, indicating that failure events are rare.

---

## Model Evaluation Metrics

1. **Overall Model Accuracy**: 
   - Best Model Accuracy with Threshold 0.6: **98.60%**.
   
2. **Classification Report**:

   | Metric      | Class 0 | Class 1 | Average |
   |-------------|---------|---------|---------|
   | Precision   | 0.99    | 0.92    | 0.95    |
   | Recall      | 1.00    | 0.65    | 0.82    |
   | F1-Score    | 0.99    | 0.76    | 0.88    |
   | Support     | 1932    | 68      | 2000    |

3. **Confusion Matrix**:

   ![Confusion Matrix](https://github.com/Volcann/Predictive-Maintenance/blob/bb1c21a0e1442b00df86794bac61c795bc2edacc/Unknown-4.png)

   - **True Positives (TP)**: 44 
   - **True Negatives (TN)**: 1928 
   - **False Positives (FP)**: 4 
   - **False Negatives (FN)**: 24 

### Summary

The model achieves a high overall accuracy of 98.60%, demonstrating effective classification. However, challenges persist in identifying the minority class (class 1). Strategies to enhance detection may include dataset rebalancing or the exploration of alternative algorithms.

---

## ROC (Receiver Operating Characteristic) Curve

The ROC curve is a graphical tool used to evaluate the performance of a binary classification model, illustrating the trade-off between the true positive rate (TPR) and the false positive rate (FPR) across various threshold settings. 

![ROC (Receiver Operating Characteristic) Curve](https://github.com/Volcann/Predictive-Maintenance/blob/bb1c21a0e1442b00df86794bac61c795bc2edacc/Unknown-3.png)

### Key Concepts

- **True Positive Rate (TPR)**: The proportion of actual positive cases accurately identified.

  **TPR = TP / (TP + FN)**

- **False Positive Rate (FPR)**: The proportion of actual negative cases incorrectly classified as positive.

  **FPR = FP / (FP + TN)**

- **Threshold**: The decision boundary for classification; for instance, a threshold of 0.6 indicates that predictions greater than or equal to 0.6 are classified as positive.

### ROC Curve Analysis

At a threshold of 0.6, the model achieves a TPR of approximately 0.65 and an FPR of approximately 0.00207.

### Area Under the Curve (AUC)

The AUC summarizes model performance across thresholds, where a value of 1 represents a perfect model, while a value of 0.5 indicates no discriminative ability.

---

## Interpretation of Key Predictive Features

The features **Tool Wear [min]**, **Torque [Nm]**, and **Rotational Speed [rpm]** demonstrate the highest statistical correlation with the target variable, marking them as significant predictors. In contrast, features like **Air Temperature [K]** and **Process Temperature [K]** exhibit minimal contribution, suggesting potential redundancy or irrelevance.

![Interpretation of Key Predictive Features](https://github.com/Volcann/Predictive-Maintenance/blob/bb1c21a0e1442b00df86794bac61c795bc2edacc/Unknown-1.png)

---

## Conclusion

This repository offers valuable insights into predictive maintenance through a synthetic dataset and model evaluation metrics. By leveraging machine learning techniques alongside domain knowledge, organizations can effectively develop predictive maintenance strategies, leading to enhanced operational efficiency and reduced downtime.
