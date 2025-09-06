# AI-Driven Cardiovascular Risk Prediction Engine

## 📋 Project Overview

This project implements a **Time Series Transformer-based Risk Prediction Engine** designed to forecast cardiovascular deterioration (e.g., heart attack or cardiac arrest) in chronic care patients within the next 90 days. The model leverages 30–180 days of historical patient data, including vitals, lab results, medication adherence, and lifestyle logs.

## 🚀 Features

* Transformer-based architecture (Informer / Time Series Transformer).
* Handles sequential time-series input data.
* Predicts the probability of cardiovascular deterioration in the next 90 days.
* Provides global and local explainability for model decisions.
* Includes a prototype dashboard for visualizing patient risk scores and explanations.

## ✅ Dataset

Recommended Dataset:

* **MIMIC-III (Medical Information Mart for Intensive Care)**: Comprehensive time-series dataset with patient vitals, lab results, medications, and outcomes over time.

  * Access: [https://mimic.physionet.org/](https://mimic.physionet.org/)

Alternative (For prototype purposes only):

* **Heart Failure Prediction Dataset (Kaggle)**

  * URL: [https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction)
  * Limitation: Static snapshot data only; no time-series information.

## 🏗️ Project Structure

```
cardio-risk-predictor/
├── data/               # Dataset files (MIMIC-III or Heart Failure Dataset)
├── models/             # Transformer model implementations and saved checkpoints
├── notebooks/          # Jupyter notebooks for exploration and prototyping
├── src/                # Core source code (data preprocessing, model, evaluation, explainability)
├── prototype/          # Streamlit or Dash-based dashboard for visualization
├── requirements.txt    # Python dependencies
├── README.md           # Project description
└── config.yaml         # Config file for parameters (sequence length, feature list, etc.)
```

## ⚡ Model Approach

* Input: Sequence of patient data (shape: \[batch\_size, sequence\_length=180, feature\_dim=20+])
* Architecture: Time Series Transformer (Informer) → MLP head → Sigmoid output (risk probability).
* Output: Probability score between 0 and 1.

## 📊 Evaluation Metrics

* AUROC
* AUPRC
* Calibration Plot
* Confusion Matrix
* Brier Score

## 💡 Explainability

* Global: Feature importance across all patients (e.g., elevated troponin, poor HRV, rising cholesterol).
* Local: Patient-specific explanations using attention weights or SHAP waterfall plots.

## 🌐 Prototype Dashboard

Link: [https://cardio-risk-predictor.streamlit.app](https://cardio-risk-predictor.streamlit.app) (example)

## 🎯 Next Step

* Integrate real-time data source (MIMIC-III).
* Deploy production-grade model pipeline.
* Collaborate with clinicians for validation and actionable insights.

---

