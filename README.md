# Fraud Detection System

A beginner-friendly Machine Learning project for detecting fraudulent financial transactions using **Logistic Regression** and **SMOTE**.

---

## 📌 Project Overview

Fraudulent transactions are rare compared with legitimate transactions, making fraud detection a highly imbalanced classification problem.

This project builds a simple fraud detection system using supervised Machine Learning and evaluates its performance using fraud-focused metrics such as:

- Precision
- Recall
- F1-Score
- ROC-AUC

---

## 🎯 Problem Statement

The goal is to classify financial transactions as:

- `0` → Legitimate
- `1` → Fraudulent

---

## 📊 Dataset

The project uses the publicly available **PaySim Financial Transactions Dataset**.

The dataset contains more than **6.3 million transactions** with information about:

- Transaction type
- Transaction amount
- Account balances
- Fraud labels

Due to the large dataset size and severe class imbalance, appropriate preprocessing and sampling techniques were required.

---

## 🧩 Features

The final dataset contains the following features:

- `step`
- `type`
- `amount`
- `oldbalanceOrg`
- `newbalanceOrig`
- `oldbalanceDest`
- `newbalanceDest`
- `isFlaggedFraud`

### Target Variable

- `isFraud`

Where:

- `0` → Legitimate transaction
- `1` → Fraudulent transaction

High-cardinality account identifiers such as `nameOrig` and `nameDest` were removed during data cleaning.

---

## 🛠️ Technologies Used

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **Scikit-learn**
- **Imbalanced-learn**
- **Joblib**
- **Jupyter Notebook**

---

## 📁 Project Structure

```text
Fraud-Detection-System/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── 01_Data_Understanding.ipynb
│   ├── 02_Data_Cleaning.ipynb
│   ├── 03_EDA.ipynb
│   ├── 04_Preprocessing.ipynb
│   ├── 05_Model_Training.ipynb
│   └── 06_Model_Evaluation.ipynb
│
├── src/
│   ├── data_cleaning.py
│   ├── preprocessing.py
│   └── model.py
│
├── models/
│   ├── fraud_detection_model.pkl
│   └── fraud_detection_preprocessor.pkl
│
├── images/
│
├── reports/
│
├── requirements.txt
├── README.md
└── LICENSE
```
---


## Project Workflow

Data Understanding
        ↓
Data Cleaning
        ↓
Exploratory Data Analysis
        ↓
Data Preprocessing
        ↓
Train/Test Split
        ↓
Baseline Logistic Regression
        ↓
SMOTE
        ↓
Logistic Regression + SMOTE
        ↓
Model Evaluation
        ↓
Final Prediction System

---


## 📈 EDA Highlights

Some important findings from the exploratory data analysis:

- `Fraudulent transactions represent only about 0.13% of the dataset.`
- `Fraud was concentrated mainly in TRANSFER and CASH_OUT transactions.`
- `Fraudulent transactions had a higher average transaction amount.`
- `Fraud transaction amounts were strongly right-skewed.`
- `Several balance-related features showed high correlation with each other.`
- `The severe class imbalance makes accuracy alone unsuitable for evaluating the model.`

---


## 🤖 Models Used

Three approaches were evaluated:

### 1. Logistic Regression

A baseline supervised classification model was trained on the original imbalanced dataset.

### 2. Logistic Regression + SMOTE

SMOTE (Synthetic Minority Over-sampling Technique) was used to address class imbalance by generating synthetic examples of the minority fraud class.

### 3. Isolation Forest

An anomaly detection approach was also tested as an unsupervised baseline.


---


## 📊 Model Comparison

| Model                           |  Precision |     Recall |   F1-Score |    ROC-AUC |
| ------------------------------- | ---------: | ---------: | ---------: | ---------: |
| Logistic Regression             |     91.36% |     40.54% |     56.16% |     97.38% |
| **Logistic Regression + SMOTE** | **67.44%** | **59.89%** | **63.44%** | **99.23%** |
| Isolation Forest                |      1.41% |     13.64% |      2.56% |          — |


---


## 🏆 Final Model

Logistic Regression + SMOTE was selected as the final model.

| Metric    |      Score |
| --------- | ---------: |
| Precision | **67.44%** |
| Recall    | **59.89%** |
| F1-Score  | **63.44%** |
| ROC-AUC   | **99.23%** |

---


## 🧠 Why SMOTE?

The dataset contains a very small percentage of fraudulent transactions compared with legitimate transactions.

This creates a class imbalance problem where a model can achieve high accuracy while performing poorly on fraud detection.

SMOTE helps address this problem by generating synthetic samples for the minority class.

In this project, SMOTE improved:

- Recall
- F1-Score
- ROC-AUC

compared with the baseline Logistic Regression model.

---


## 📏 Evaluation Metrics

Because fraud detection is an imbalanced classification problem, multiple evaluation metrics were considered.

**Precision**

Measures how many transactions predicted as fraud were actually fraudulent.

**Recall**

Measures how many actual fraudulent transactions were successfully detected.

**F1-Score**

Provides a balance between precision and recall.

**ROC-AUC**

Measures the model's ability to distinguish between legitimate and fraudulent transactions across different classification thresholds.

---

## 🚀 How to Run

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd Fraud-Detection-System
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the Notebooks


**Open Jupyter Notebook:**

```bash
jupyter notebook
```

---

Run the notebooks in order:

01_Data_Understanding.ipynb
        ↓
02_Data_Cleaning.ipynb
        ↓
03_EDA.ipynb
        ↓
04_Preprocessing.ipynb
        ↓
05_Model_Training.ipynb
        ↓
06_Model_Evaluation.ipynb

---

## 👨‍💻 Author

**Suhail**

- GitHub: *https://github.com/ss2954614-byte*
- LinkedIn: *www.linkedin.com/in/suhailai*
- Portfolio: *https://suhailai.lovable.app/*

---

## 📄 License

This project is licensed under the MIT License.

---
