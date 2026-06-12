# Early Sepsis Onset Prediction Using ICU Time-Series Data
I used kaggle notebook
## Overview

This project develops a machine learning pipeline for early prediction of sepsis onset using the PhysioNet/Computing in Cardiology Challenge 2019 dataset.

The objective is to predict sepsis approximately 6 hours before physician diagnosis while addressing several real-world challenges:

* High missing-value rates
* Irregularly sampled ICU measurements
* Severe class imbalance
* Noisy clinical labels
* Temporal data leakage

The pipeline includes:

* Exploratory Data Analysis (EDA)
* Missing value handling
* Temporal feature engineering
* Label noise mitigation
* Logistic Regression baseline model
* LightGBM model
* Performance evaluation and threshold selection

---

## Repository Structure

```text
.
├── sepsisclassification.ipynb
├── requirements.txt
├── README.md
│
├── report/
│   └── Sepsis_Prediction_Report.pdf
│
├── outputs/
│   ├── REPORT_class_imbalance.png
│   ├── REPORT_missingness_heatmap.png
│   ├── ...
│
├── models/
│   ├── baseline_model.pkl
│   ├── lgbm_model.pkl
│   └── ...
│
└── results/
    ├── baseline_metrics.json
    ├── lgbm_metrics.json
    └── ...
```

## Dataset

This repository does **not** include the dataset.

The project uses the PhysioNet Challenge 2019 dataset:

**Dataset Page**

https://physionet.org/content/challenge-2019/1.0.0/

PhysioNet requires users to create an account and accept the data usage agreement before downloading the files.

---

## Downloading the Dataset

After obtaining access from PhysioNet, download the training data.

```bash
mkdir challenge2019
cd challenge2019

wget -r -N -c -np https://physionet.org/files/challenge-2019/1.0.0/training/
```

### Alternative Download

You may also download the dataset manually from the PhysioNet website and extract it locally.

Expected folders:

```text
training/
├── training_setA/
└── training_setB/
```

---

## Running on Kaggle

### Step 1: Upload Dataset

1. Create a new Kaggle Dataset.
2. Upload:

   * training_setA
   * training_setB
3. Wait for processing to complete.

### Step 2: Open Notebook

1. Create a new Kaggle Notebook.
2. Upload `sepsisclassification.ipynb`.
3. Attach your uploaded dataset using the **Add Input** button.

### Step 3: Update Dataset Paths

If necessary, modify:

```python
DIR_A = "/kaggle/input/<dataset-name>/training_setA"
DIR_B = "/kaggle/input/<dataset-name>/training_setB"
```

Replace `<dataset-name>` with your Kaggle dataset name.

### Step 4: Run All Cells

Select:

```text
Run All
```

The notebook will:

1. Load raw patient files
2. Perform EDA
3. Create train/validation/test splits
4. Generate engineered features
5. Apply label-noise mitigation
6. Train baseline Logistic Regression
7. Train LightGBM
8. Save figures and evaluation results

---

## Running Locally

### Create Environment

```powershell
python -m venv venv
venv\Scripts\activate
```

### Launch Notebook

```bash
jupyter notebook
```

Open:

```text
sepsisclassification.ipynb
```

and run all cells.

---

## Expected Outputs

The notebook generates:

### Figures

* Missingness analysis
* Class imbalance plots
* Data split summaries
* Label noise statistics
* Feature importance plots
* ROC curves
* Precision-Recall curves
* Confusion matrices

### Models

* Logistic Regression baseline
* LightGBM model

### Evaluation Results

* AUROC
* AUPRC
* Precision
* Recall
* F1 Score
* Confusion Matrix

---

### Modeling

* Logistic Regression baseline
* LightGBM classifier

### Evaluation

* Temporal validation
* AUROC
* AUPRC
* Threshold optimization

---

## Author

Muhammad Ibrahim
AI Internship Screening Task
June 2026
