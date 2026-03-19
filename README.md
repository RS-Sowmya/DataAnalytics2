# MachineLearning1
# Instructor Effectiveness Analysis (EdTech ML Project)
## Overview
This project analyzes instructor performance in an EdTech platform using data driven methods. It combines statistical techniques and machine learning to evaluate, rank, and predict instructor effectiveness based on student engagement and learning outcomes.

## Objectives
Identify key factors influencing instructor performance
Create a robust **Instructor Effectiveness Score**
Classify instructors into:
  * Low
  * Medium
  * High effectiveness tiers
Build a machine learning model to predict instructor performance
Generate actionable insights for improving learning outcomes

## Dataset Features
The dataset contains batch-level metrics such as:
* Completion rate
* Dropout rate
* Quiz scores & score improvement
* Watch time & engagement metrics
* Assignment submission rate
* Forum activity
* Feedback score & response rate

## Exploratory Data Analysis (EDA)
* Analyzed distributions and relationships between features
* Identified a strong negative correlation between:
* Completion rate and dropout rate
* Observed that engagement metrics positively influence performance
  
## Instructor Effectiveness Score
* Used **PCA (Principal Component Analysis)** to derive a composite score
* Adjusted PCA direction using domain knowledge:
* Higher completion → better performance
* Higher dropout → worse performance
* Normalized scores and divided into:
* Low / Medium / High tiers

## Instructor-Level Aggregation
Since instructors teach multiple batches:
* Aggregated batch-level data using:
   * Mean → overall performance
   * Standard deviation → consistency
   * Count → number of batches (experience)
* Introduced **experience weight** to reward consistent performance over multiple batches

## Machine Learning Model
* Model used: **Random Forest Classifier**
* Inputs: Aggregated instructor features
* Output: Effectiveness tier
  
## Model Evaluation
* Accuracy: ~92%
* Metrics used:
  * Precision
  * Recall
  * F1-score
* Key observations:
  * Strong detection of low-performing instructors (high recall)
  * High precision for top-performing instructors
  * Minor confusion between Medium and High tiers
  * 
## Key Insights
* **Dropout rate** is the strongest negative indicator
* **Completion rate & engagement metrics** drive effectiveness
* Low-performing instructors are clearly distinguishable
* Medium vs High performers require more contextual features

## Business Impact
* Early detection of low-performing instructors
* Personalized instructor training programs
* Improved course design and student retention
* Data-driven instructor ranking and rewards

## Important Learnings
* PCA requires **direction correction** using domain knowledge
* Avoid **data leakage** when building ML models
* Aggregation strategy significantly affects results

## Used libraries
* Python
* Pandas, NumPy
* Scikit-learn
* Matplotlib, Seaborn

## 📌 Future Improvements
* Add SHAP for explainability
* Try XGBoost / LightGBM
* Include course difficulty & student demographics
* Build a real-time dashboard (Streamlit)

