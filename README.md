
# NetworkSecurity\_DS\_Project

A machine learning pipeline for detecting phishing websites using structured web-based features, scalable infrastructure, and production-ready deployment.

🔗 **GitHub Repository**: [NetworkSecurity\_DS\_Project](https://github.com/HamzaImtiaz03/NetworkSecurity_DS_Project/tree/main)

---

## 📌 Project Summary

**NetworkSecurity\_DS\_Project** is an end-to-end data science solution designed to detect phishing websites with high accuracy. Using a structured dataset (`phisingData.csv`) of 11,055 samples and 30+ handcrafted features, the system builds a reliable classification pipeline that integrates data engineering, model training, experiment tracking, and API deployment.

---

## 🎯 Objective

The goal is to automate the identification of phishing websites to enhance online security. The pipeline:

* Processes and validates the dataset.
* Trains and evaluates multiple machine learning models.
* Deploys the best-performing model with real-time prediction capability via FastAPI.
* Ensures scalability and reproducibility with MongoDB, AWS S3, and MLflow.

---

## 🧱 Project Architecture

### 1. **Data Ingestion**

* Loads raw dataset from MongoDB.
* Performs train-test split and initial checks.
* Scripts: `push_data.py`, `data_ingestion.py`

### 2. **Data Validation**

* Confirms dataset schema (31 columns expected).
* Performs data drift analysis using the Kolmogorov–Smirnov (KS) test.
* Script: `data_validation.py`

### 3. **Data Transformation**

* Applies missing value imputation via `KNNImputer`.
* Encodes categorical target variable.
* Script: `data_transformation.py`

### 4. **Model Training**

* Trains multiple models: Random Forest, Logistic Regression, etc.
* Selects the best model based on F1-score (\~95–97%).
* Logs experiments and metrics using MLflow.
* Script: `model_trainer.py`

### 5. **Model Deployment**

* Executes the full pipeline through `training_pipeline.py` and `main.py`.
* Stores models and artifacts on AWS S3.
* Exposes a FastAPI endpoint (`app.py`) for inference and integration.

---

## 🔍 Key Features

* **High Accuracy**: Achieves 99% F1-score,98% precision, 99% recall-score on phishing detection.
* **Scalable Infrastructure**: Uses MongoDB and AWS S3 for flexible data and model storage.
* **Reproducibility**: MLflow ensures all training runs are tracked and reproducible.
* **Real-Time Prediction**: FastAPI provides a lightweight, RESTful interface for predictions.
* **Production-Ready**: Suitable for integration into larger systems such as browser extensions or cybersecurity dashboards.

---

## 🧰 Tech Stack

| Category             | Tools/Technologies             |
| -------------------- | ------------------------------ |
| Programming Language | Python                         |
| Data Processing      | pandas, scikit-learn           |
| Database             | MongoDB                        |
| Experiment Tracking  | MLflow                         |
| API Deployment       | FastAPI                        |
| Cloud Storage        | AWS S3                         |
| Packaging            | `requirements.txt`, `setup.py` |

---

## ⚠️ Limitations

* The model contains all the necessary code for cloud deployment,it'll be deployed on cloud platforms in future.
* Real-time feature extraction from live web traffic is not implemented and would require additional infrastructure.

---

## 📈 Business & Social Impact

Phishing attacks account for billions of dollars in losses annually. This project provides:

* An intelligent, automated method to combat online fraud.
* A reproducible and extensible framework for cybersecurity research.
* A deployable system that could integrate into end-user applications for real-time protection.

---

## 📂 Repository Structure

```
NetworkSecurity_DS_Project/
│
├── app.py                        # FastAPI app for model inference
├── main.py                       # Main entry point for pipeline execution
├── push_data.py                  # Pushes data to MongoDB
├── training_pipeline.py          # Orchestrates end-to-end pipeline
├── data_ingestion.py             # Loads and splits data
├── data_validation.py            # Schema and drift validation
├── data_transformation.py        # Imputation and label transformation
├── model_trainer.py              # Trains and logs ML models
├── requirements.txt              # Project dependencies
├── setup.py                      # Package setup
└── phisingData.csv               # Source dataset
```

---

## 📎 Reference Link

🔗 **GitHub Repository**: [https://github.com/HamzaImtiaz03/NetworkSecurity\_DS\_Project/tree/main](https://github.com/HamzaImtiaz03/NetworkSecurity_DS_Project/tree/main)

---














### Network Security Projects For Phising Data

Setup github secrets:
AWS_ACCESS_KEY_ID=

AWS_SECRET_ACCESS_KEY=

AWS_REGION = us-east-1

AWS_ECR_LOGIN_URI = 788614365622.dkr.ecr.us-east-1.amazonaws.com/networkssecurity
ECR_REPOSITORY_NAME = networkssecurity


Docker Setup In EC2 commands to be Executed
#optinal

sudo apt-get update -y

sudo apt-get upgrade

#required

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker