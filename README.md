# Diabetes Diagnosis Classification Using Decision Tree and Naive Bayes

## Overview
This project is the outcome of a final assignment for the Intelligent Systems course at Telkom University Surabaya. It involves a comparative analysis of Decision Tree and Naive Bayes models for classifying diabetes using a dataset from Medical City Hospital and the Specializes Center for Endocrinology and Diabetes, Al-Kindy Teaching Hospital in Iraq. The dataset comprises medical and laboratory data from 1,000 patients, including features such as age, gender, HbA1c, lipid profile, BMI, and diabetes status (Diabetic, Non-Diabetic, or Prediabetic).

## Background
Diabetes Mellitus impacts 537 million people worldwide and is expected to increase to 783 million by 2045, posing significant health complications. Accurate diagnosis is critical, and machine learning can enhance clinical decision-making. This study utilizes a dataset from two Iraqi hospitals to build and evaluate classification models.

## Methodology
- **Data Preprocessing**: Involved standardization, encoding of categorical variables, outlier handling, feature selection, and data transformation with stratified sampling (80:20 split).
- **Modeling**: Employed Gaussian Naive Bayes and Decision Tree algorithms.
- **Evaluation**: Models were assessed using accuracy, precision, recall, F1-score, and ROC-AUC metrics.
- **Tuning**: Hyperparameter optimization was performed using grid search with the following parameters:
  - **Decision Tree**: 
    - `max_depth`: [3, 5, 7, 10] (controls tree depth and overfitting risk)
    - `min_samples_split`: [2, 5, 10] (minimum samples for split node to prevent over-splitting)
    - `min_samples_leaf`: [1, 2, 4] (minimum samples per leaf to avoid leaves with few data)
  - **Naive Bayes**: 
    - `var_smoothing`: [1.0, 1e-1, 1e-2, ..., 1e-9] (small variance addition for numerical stability)
- **Data Transformation**: Included normalization and handling of class imbalance using SMOTE.

## Results
The following table summarizes the performance of the models:

| Model         | Tuning         | Accuracy | F1-Score | Misclassifications | Overfitting Status | F1-Score Improvement | Conclusion                                      |
|---------------|----------------|----------|----------|--------------------|---------------------|----------------------|-------------------------------------------------|
| Naive Bayes   | Without Tuning | 0.9665   | 0.9666   | 17                 | Not Overfitting     | -                    | Tuning slightly helps but not significant       |
| Naive Bayes   | With Tuning    | 0.9724   | 0.9725   | 14                 | Not Overfitting     | 0.0059              |                                                 |
| Decision Tree | Without Tuning | 0.9980   | 0.9981   | 1                  | Not Overfitting     | -                    | Without tuning already excellent, tuning unnecessary |
| Decision Tree | With Tuning    | 0.9961   | 0.9962   | 2                  | Not Overfitting     | -0.0019             |                                                 |

- **Key Findings**:
  - Decision Tree without tuning outperformed all other models, achieving near-perfect accuracy (0.9980) and F1-score (0.9981) with only 1 misclassification.
  - Decision Tree with tuning showed a slight performance drop (accuracy: 0.9961, F1-score: 0.9962).
  - Naive Bayes with tuning improved slightly over its untuned version (F1-score improvement of 0.0059), but still lagged behind Decision Tree.
  - Decision Tree significantly outperformed Naive Bayes in both accuracy and F1-score, with minimal errors.

## Recommendations
- Utilize the Decision Tree model without tuning for the best diabetes classification results in this context, given its high accuracy and minimal misclassifications.
- Further studies could investigate additional features or advanced tuning methods to refine model performance.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments
Grateful acknowledgment to the Intelligent Systems course instructors and Telkom University Surabaya for their support and resources.
