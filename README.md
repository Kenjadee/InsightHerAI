# InsightHerAI

AI-powered maternal health risk triage system that helps frontline health workers make faster, more confident decisions.

# Overview

InsightHerAI is a machine learning triage tool that is designed to assess the maternal health risk level from routine patient vitals. The system classifies patients into Low, Mid, or High risk categories and returns a confidence score to support cliical decision making. It is designed to flag uncertain cases for escalation before they become emergencies. InsightHerAI is built for settings where specialist access is limited and speed matters.

# The Problem

Maternal mortality has remained a critical public health challenge for years, particularly in low-resource settings. Frontline health workers often lack the tools to quickly classify risk levels from routine vitals, leading to delayed intervention. InsightHerAI helps bridge that gap.

# Features

1) Risk classification - Low / Mid / High risk from 6 common vitals
2) Confidence scoring - flags uncertain predictions for human review
3) Random Forest model - strong, interpretable, and handles small datasets well
4) Multi-model benchmarking - Logistic Regression, Decision Tree, and Random Forest compared
5) Feature importance analysis - understand which vitals drive predictions

# Input Features

Age - Patient age in years
SystolicBP - Systolic blood pressure (mmHg)
DiastolicBP - Diastolic blood pressure (mmHg)
BS - Blood glucose level (mmol/L)
BodyTemp - Body temperature (°F)
HeartRate - Resting heart rate (bpm)

# Dataset

Maternal Health Risk Data Set - sourced from IoT-based risk monitoring systems across hospitals, community clinics, and rural health posts.

Features: Age, Blood Pressure (Systolic/Diastolic), Blood Sugar, Body Temperature, Heart Rate

Target: Risk Level (Low / Mid / High)

Dataset: https://www.kaggle.com/datasets/csafrit2/maternal-health-risk-data

# Model Pipeline

1) Data loading and preprocessing
2) Risk level encoding
3) Train-test split with stratification
4) Feature scaling using StandardScaler
5) Model training and benchmarking
6) Evaluation using:
  Accuracy Score
  Classification Report
  Confusion Matrix
  ROC-AUC Score
7) Feature importance extraction
8) Confidence-based triage prediction system

# Model Performance

The project makes use of multiple machine learning models before selecting the final deployment model.

Model -	Purpose
Logistic Regression	- Baseline linear classifier
Decision - Tree	Rule-based classification comparison
Random Forest	- Final selected model for deployment

The Random Forest model achieved the strongest overall performance and was selected because it:
1)Handles small healthcare datasets effectively
2)Reduces overfitting compared to single trees
3)Produces interpretable feature importance scores
4)Performs well on nonlinear relationships between vitals and risk

Model -	Accuracy - 	High Risk Recall

Logistic Regression -	64% -	0.82
Decision Tree -	84% -	0.96
Random Forest -	85% -	0.96

AUC Score: 0.957

# Confidence Scoring System

InsightHerAI does not only predict a risk category, it also measures prediction confidence.

Confidence - Level -	Meaning

High Confidence -	Strong prediction - certainty
Low Confidence - Suggest Review -	Requires additional human review
Uncertain - Escalate to Senior Worker -	Immediate escalation recommended

Confidence ≥ 85% → High Confidence
60–84% → Suggest Review
< 60% → Escalate

# Feature Importance

The system also analyzes which patient vitals contribute most strongly to maternal risk prediction. This improves transparency and helps support interpretability in healthcare AI systems.

Examples of influential features include:
1) Blood Sugar (BS)
2) Systolic Blood Pressure
3) Body Temperature
4) Heart Rate

# Future Improvements

- Deploy as a web application using Flask or FastAPI
- Add real-time patient dashboards
- Integrate explainable AI visualizations (SHAP/LIME)
- Expand training data from additional healthcare sources
- Add multilingual support for broader accessibility
- Build offline-first support for rural environments
- Integrate SMS alert escalation for critical predictions

# Limitations
- Small dataset (1,014 patients) — may affect generalisation
- Not clinically validated
- Should not replace professional medical judgment

# How to Run
1. Open the notebook in Google Colab
2. Run all cells from top to bottom
3. Use the prediction function with patient vitals
4. Interpret the triage decision and confidence score

# Disclaimer

InsightHerAI is an educational machine learning project. It is not intended to replace licensed medical professionals or clinical judgment. Predictions should always be reviewed within proper healthcare workflows.

# Author

Obi Ebube
