# User Manual

## Federated Learning for Early Cardiovascular Disease Prediction

---

## 1. Purpose

This notebook enables users to:

* Build a cardiovascular disease prediction dataset from MIMIC-III.
* Train centralised machine learning models.
* Simulate federated learning environments.
* Compare centralised and federated learning performance.

---

## 2. Prerequisites

### Software Requirements

* Python 3.10+
* Google Colab (recommended)
* Google Drive access

### Dataset Requirement

MIMIC-III Clinical Database v1.4

Store dataset files inside:

/content/drive/MyDrive/MIMIC-III/data/mimic-iii-clinical-database-1.4/

---

## 3. Running the Notebook

### Step 1: Mount Google Drive

Run:

```python
from google.colab import drive
drive.mount('/content/drive')
```

Authorize access when prompted.

---

### Step 2: Configure Dataset Path

Verify:

```python
BASE_PATH = "/content/drive/MyDrive/MIMIC-III/data/mimic-iii-clinical-database-1.4/"
```

Modify if your dataset is stored elsewhere.

---

### Step 3: Load MIMIC-III Tables

Execute the Data Loading section.

Expected output:

* PATIENTS
* ADMISSIONS
* DIAGNOSES_ICD
* D_ICD_DIAGNOSES

loaded successfully.

---

### Step 4: Explore Dataset

Run Dataset Exploration.

This section displays:

* Missing values
* Number of patients
* Number of admissions
* Number of CVD patients

---

### Step 5: Feature Extraction

Run:

* CVD Label Creation
* Age and Gender Extraction
* Glucose Extraction
* Cholesterol Extraction
* Vital Sign Extraction

Outputs generated:

* labels
* demo
* glucose
* cholesterol
* vitals

---

### Step 6: Dataset Construction

Run Dataset Construction.

Expected output:

```python
final_df.shape
```

Dataset containing all engineered features.

---

### Step 7: Data Cleaning

Execute:

* Duplicate removal
* Missing value analysis
* Outlier detection
* Clinical range cleaning

---

### Step 8: Missing Value Imputation

Median imputation is applied automatically.

Features processed:

* AGE
* GENDER
* GLUCOSE
* CHOLESTEROL
* HEART_RATE
* SYS_BP
* DIA_BP

---

### Step 9: Feature Scaling

StandardScaler is applied.

All numerical features are standardised before modelling.

---

### Step 10: Save Processed Dataset

Run:

```python
final_df.to_csv(
"/content/drive/MyDrive/MIMIC-III/final_cvd_dataset.csv",
index=False
)
```

Output:

final_cvd_dataset.csv

---

## 4. Centralised Model Training

### Logistic Regression

Run:

* Logistic Regression Baseline
* Evaluation

Outputs:

* Accuracy
* Precision
* Recall
* F1 Score
* AUC

---

### Random Forest

Run:

* Random Forest
* Evaluation

Outputs:

* Accuracy
* Precision
* Recall
* F1 Score
* AUC

---

### Neural Network

Run:

* create_model()
* Centralised Neural Network
* Evaluate

Outputs:

* Training history
* Performance metrics

---

## 5. Federated Learning Execution

### Create Clients

Run:

Create 10 Hospitals (IID Scenario)

Output:

10 client datasets.

---

### Run Federated Training

Execute:

Federated Training

Configuration:

* 50 communication rounds
* 5 local epochs
* FedAvg aggregation

Expected runtime:

20–60 minutes depending on hardware.

---

### Evaluate Federated Model

Run:

Final Evaluation

Metrics produced:

* Accuracy
* Precision
* Recall
* F1 Score
* AUC

---

## 6. Generated Outputs

### Dataset

final_cvd_dataset.csv

### Visualisations

* Missing value chart
* Outlier boxplots
* Federated convergence graph

### Model Outputs

* Logistic Regression results
* Random Forest results
* Neural Network results
* Federated Learning results

---

## 7. Troubleshooting

### Google Drive Not Mounted

Run:

```python
drive.mount('/content/drive')
```

again.

---

### File Not Found Error

Verify:

* Dataset location
* BASE_PATH value
* File names

---

### Memory Issues

Use:

```python
chunksize=1000000
```

for large MIMIC tables.

---

### TensorFlow Errors

Restart runtime and rerun all cells sequentially.

---

## 8. Expected Outcome

After successful execution, users will obtain:

* Clean cardiovascular dataset
* Centralised ML models
* Federated Learning model
* Comparative performance metrics
* Publication-ready experimental results
