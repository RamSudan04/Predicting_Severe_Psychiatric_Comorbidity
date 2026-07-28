# Predicting Severe Psychiatric Comorbidity Using XGBoost and SHAP

## 💡 Brief Idea
Mental health is a critical component of overall well-being, yet a significant challenge in modern psychiatry is the high prevalence of comorbidity—where a patient suffers from two or more distinct mental health conditions simultaneously. 

This project applies a comprehensive machine learning framework using **R** to the **Galicia Clinical Dataset** (2,300 patients) to uncover hidden patient subgroups. The primary objective is to develop a predictive, interpretable tool using **XGBoost** and **SHAP** to automatically identify patients at high risk of severe psychiatric comorbidity (defined as having 3 or more concurrent disorders).

## 🛠️ Methodology
* **Data Preprocessing & Engineering:** Processed demographic and clinical variables, including 61 binary features representing specific psychiatric diagnoses across Axis I and Axis II. Engineered a `comorbidity_count` to quantify illness burden and classify patients into risk categories.
* **Unsupervised Clustering:** Applied algorithms like K-Means and Hierarchical clustering natively in R to segment patients into clinically interpretable profiles and analyze pairwise comorbidity structures across demographics.
* **Predictive Modeling:** Trained an Extreme Gradient Boosting (XGBoost) classifier to model complex, non-linear clinical relationships. The model was validated using an 80/20 stratified Train-Test split with rigorous hyperparameter tuning via Cross-Validation.
* **Explainable AI:** Integrated SHAP (SHapley Additive exPlanations) to interpret predictions, unpacking the "black box" model to provide feature-level transparency for clinical trust.

## 🔍 Findings
* **Clustering Discoveries:** Unsupervised clustering revealed a dominant "High-Complexity Profile" alongside specific, nested profiles such as "Major Depression," "Generalized Anxiety," and distinct Borderline Personality Disorder (BPD) and PTSD profiles. 
* **Clinical Drivers of Risk:** Through SHAP cooperative game theory analysis, the top clinical features quantitatively driving a "High Risk" classification were identified as:
  1. Dysthymia
  2. Substance-Induced Anxiety
  3. Borderline Personality Disorder
  4. Personality Disorder NOS
  5. Substance-Induced Mood Disorder

## 📊 Results
The optimized XGBoost model demonstrated exceptional performance when classifying the unseen test set (460 patients):

| Metric | Score | Clinical Significance |
| :--- | :--- | :--- |
| **Overall Accuracy** | **97%** | Highly reliable overall classification across the cohort. |
| **Recall (High Risk)** | **1.00** | **0 False Negatives.** The model successfully identified *every single* high-risk patient. |
| **Precision (High Risk)**| **0.97** | Very low rate of false alarms when predicting high comorbidity risk. |
## 👤 Project Owner
**Ram Sudan**
