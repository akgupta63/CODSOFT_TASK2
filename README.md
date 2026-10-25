# CODSOFT_TASK2

Project README: Credit Card Fraud Detection
This project implements a machine learning solution to detect fraudulent credit card transactions using a simulated transaction dataset.

1. Project Overview
Credit card fraud detection is a classic highly-imbalanced classification problem. In this project, we preprocess transaction logs, engineer relevant behavioral features, and train multiple classifiers to effectively flag fraudulent events while minimizing false positives.

2. Dataset
Source: fraudTest.csv (unzipped from /content/fraudTest.csv.zip)
Size: 555,719 rows, 23 columns
Class Imbalance: Extreme (~0.38% fraud, ~99.62% legitimate)
3. Feature Engineering & Preprocessing
To improve classification, we prepared the features as follows:

Temporal Features: Extracted trans_hour and trans_day_of_week from the transaction timestamp.
Customer Age: Computed by subtracting date of birth (dob) from transaction timestamp.
Categorical Encoding: One-hot encoded transaction category and gender.
Scaling: Normalized numerical features (amt, geographic coordinates, population, etc.) using StandardScaler.
Data Splitting: Partitioned the dataset into 70% Training and 30% Testing sets using stratified splitting to preserve class proportions.
4. Models & Algorithms
To handle the severe class imbalance, we trained three classifiers utilizing class weight balancing:

Logistic Regression: Serves as our linear baseline.
Decision Tree: Introduces non-linear decision boundaries.
Random Forest: An ensemble of decision trees optimized for robust generalization.
5. Performance Metrics Summary
Model	AUC-ROC	Recall (Fraud)	Precision (Fraud)	F1-Score (Fraud)
Logistic Regression	0.9165	76%	3%	0.05
Decision Tree	0.9656	94%	12%	0.21
Random Forest	0.9893	89%	23%	0.36
6. Key Conclusions
Random Forest performs best overall with an AUC-ROC of 0.9893 and the highest Precision (23%), leading to the fewest false alerts.
Decision Tree provides the highest sensitivity (94% Recall), making it useful if catching every fraud instance is the top priority.
