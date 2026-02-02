# Customer Churn Prediction with Precision-First Modelling

## Overview
Customer churn prediction is a critical task for subscription-based businesses, where retention actions often come with real financial and operational costs. While many churn models focus on maximising overall accuracy, such approaches can lead to inefficient decision-making by flagging too many low-risk customers.

This project takes a **business-first approach** to churn prediction by prioritising **precision** as the primary evaluation metric. The goal is to ensure that retention efforts are directed only at customers who are highly likely to churn, making model outputs more actionable in real-world settings.

---

## Objectives
The main objectives of this project are:
- To build and compare multiple machine learning models for customer churn prediction
- To prioritise precision over accuracy based on business cost considerations
- To analyse how probability thresholds affect model performance
- To balance predictive performance with interpretability for decision-making

---

## Dataset
The project uses a telecom customer churn dataset containing demographic, service usage, billing, and contract-related features.  
The target variable indicates whether a customer churned (`Yes` / `No`).

Key feature groups include:
- Customer demographics (e.g. gender, senior citizen status)
- Contract information (e.g. contract type, tenure)
- Services subscribed (e.g. internet service, security add-ons)
- Billing and payment behaviour

---

## Data Preparation
The data preprocessing pipeline includes:
- Removal of non-informative identifiers
- Handling of invalid and missing values
- Type conversion for numerical consistency
- Exploratory analysis of categorical and numerical features
- One-hot encoding of categorical variables
- Feature scaling using `StandardScaler`

Care was taken to ensure that preprocessing steps were applied consistently across training and test sets to avoid data leakage.

---

## Modelling Approach
Four supervised learning models were trained and evaluated:

- **Logistic Regression**
- **Decision Tree**
- **Random Forest**
- **XGBoost**

All models were trained using:
- Stratified train–test splitting
- Class imbalance handling
- Hyperparameter tuning via cross-validated grid search
- Precision as the optimisation metric

This ensured a fair and consistent comparison across models.

---

## Threshold Optimisation
Rather than relying on the default classification threshold of 0.5, the project explicitly analyses predicted probabilities to understand how different thresholds affect precision and recall.

Precision–Recall curves and confusion matrices were used to identify thresholds that better align model behaviour with business objectives. This step transforms probabilistic outputs into **decision-ready predictions**.

---

## Results Summary
Key findings from the evaluation include:
- Ensemble models achieved higher raw predictive power
- Precision consistently improved when thresholds were increased above 0.5
- Logistic Regression offered the best balance between precision, recall, and interpretability
- Threshold tuning played a larger role in performance improvement than model choice alone

Based on these results, **Logistic Regression with threshold optimisation** was selected as the final model due to its stability, transparency, and strong overall balance.

---

## Feature Insights
Across models, several features consistently emerged as important churn drivers:
- Contract duration
- Customer tenure
- Internet service type (especially fibre optic)
- Payment method (notably electronic check)

The consistency of these drivers across linear, tree-based, and boosting models supports the robustness of the findings.

---

## Key Contributions and Project Highlights
- Business-driven metric selection (precision-first)
- Explicit threshold analysis and optimisation
- Fair comparison of interpretable and complex models
- Decision-aware evaluation rather than metric maximisation
- Clear linkage between model outputs and real-world actions

---

## Limitations and Future Work
While the project demonstrates strong modelling practices, several extensions are possible:
- Incorporating time-based validation to simulate real deployment scenarios
- Evaluating cost-sensitive learning with explicit monetary loss functions

---

## Conclusion
This project demonstrates an end-to-end, decision-aware machine learning workflow for churn prediction. By aligning evaluation metrics, thresholding strategies, and model selection with business objectives, the final solution delivers not just strong predictive performance, but meaningful and actionable insights.
