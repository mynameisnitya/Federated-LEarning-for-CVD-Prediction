# Federated Learning for Early Cardiovascular Disease Prediction using MIMIC-III

## Project Overview

This project investigates the use of Federated Learning (FL) for early Cardiovascular Disease (CVD) prediction using the MIMIC-III clinical database.

The notebook implements a complete machine learning pipeline including:

* Data extraction from MIMIC-III
* Feature engineering
* Data preprocessing and cleaning
* Baseline centralised machine learning models
* Federated Learning using Federated Averaging (FedAvg)
* IID client distribution experiments
* Performance evaluation and comparison

The objective is to evaluate whether Federated Learning can achieve predictive performance comparable to centralised learning while preserving data privacy.

---

## Dataset

### Source

MIMIC-III Clinical Database v1.4

### Tables Used

* PATIENTS
* ADMISSIONS
* DIAGNOSES_ICD
* D_ICD_DIAGNOSES
* LABEVENTS
* D_LABITEMS
* CHARTEVENTS
* D_ITEMS

---

## Features Used

### Demographic Features

* Age
* Gender

### Laboratory Features

* Glucose
* Cholesterol

### Vital Signs

* Heart Rate
* Systolic Blood Pressure
* Diastolic Blood Pressure

### Target Variable

* Cardiovascular Disease (CVD)

CVD labels are generated using ICD-9 codes beginning with:

39, 40, 41, 42, 43, 44, 45

---

## Data Processing Pipeline

### 1. Data Loading

Clinical tables are loaded from the MIMIC-III dataset.

### 2. Dataset Exploration

* Missing value analysis
* Dataset statistics
* Class distribution analysis

### 3. Feature Engineering

Extraction of:

* Age
* Gender
* Glucose
* Cholesterol
* Heart Rate
* Systolic BP
* Diastolic BP

### 4. Dataset Construction

All extracted features are merged into a single analytical dataset.

### 5. Data Cleaning

* Duplicate removal
* Clinical range validation
* Outlier handling

Clinical thresholds:

| Feature      | Range       |
| ------------ | ----------- |
| Heart Rate   | 20–250 bpm  |
| Systolic BP  | 50–300 mmHg |
| Diastolic BP | 20–200 mmHg |

### 6. Missing Value Treatment

Median imputation is applied.

### 7. Feature Scaling

Z-score standardisation using StandardScaler.

---

## Final Dataset

| Metric             | Value  |
| ------------------ | ------ |
| Total Records      | 52,321 |
| Features           | 7      |
| Positive CVD Cases | 38,009 |
| Negative Cases     | 14,312 |

---

## Centralised Models

### Logistic Regression

Accuracy: 88.28%

Precision: 88.67%

Recall: 96.16%

F1 Score: 92.26%

AUC: 0.905

---

### Random Forest

Accuracy: 88.03%

Precision: 90.17%

Recall: 93.74%

F1 Score: 91.92%

AUC: 0.912

---

### Neural Network

Architecture:

Input Layer (7 Features)

Dense(32, ReLU)

Dense(16, ReLU)

Dense(1, Sigmoid)

Performance:

Accuracy: 88.62%

Precision: 88.49%

Recall: 96.95%

F1 Score: 92.52%

AUC: 0.913

---

## Federated Learning Configuration

### Federated Algorithm

FedAvg (Federated Averaging)

### Experimental Setup

* 10 simulated hospitals
* IID data distribution
* 50 communication rounds
* Local training: 5 epochs per round
* Batch size: 32
* Adam optimizer
* Binary cross-entropy loss

---

## Federated Learning Results

Accuracy: 88.68%

Precision: 88.65%

Recall: 96.80%

F1 Score: 92.55%

AUC: 0.912

---

## Key Findings

* Federated Learning achieved performance comparable to centralised models.
* Privacy-preserving training was possible without sharing raw patient data.
* Neural Networks demonstrated the strongest overall performance.
* FedAvg successfully converged over multiple communication rounds.

---

## Requirements

Python 3.10+

Libraries:

* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn
* tensorflow

Install:

pip install pandas numpy matplotlib seaborn scikit-learn tensorflow

---

## Output

Generated dataset:

final_cvd_dataset.csv

Contains:

* AGE
* GENDER
* GLUCOSE
* CHOLESTEROL
* HEART_RATE
* SYS_BP
* DIA_BP
* CVD

---

## Author

Nitya Puspaceno

MSc Data Science

Nottingham Trent University

Major Project
