🦴 Bone Tumor Survival Prediction

Machine Learning & Transformer Models for Clinical Outcome Prediction

This repository contains a complete machine-learning workflow for predicting survival outcomes in bone and soft-tissue tumors using clinical, histological, and treatment-based features.
The project compares classical gradient-boosting models with modern SAINT-style tabular transformers, and includes full evaluation on train, validation, and test splits.

📂 Dataset

The dataset used in this project comes from Kaggle:

🔗 Kaggle Dataset:
https://www.kaggle.com/datasets/antimoni/bone-tumor

The dataset includes:

Patient demographic information

Tumor grade & histological subtype

MSKCC classification

Primary tumor site

Treatment modality

Final clinical status (NED, AWD, D)

🎯 Project Objectives

The goal of this project is to explore whether structured clinical features can predict:

Alive vs Dead status (binary classification)

Clinical aggressiveness of bone/soft tissue tumors

Survival-related patterns based on treatment, histology, and grade

The project focuses on imbalanced classification and interpretable ML.

🧠 Models Implemented

This repository includes:

1. XGBoost (with class weighting)

Baseline model with strong tabular performance.

2. LightGBM (with scale_pos_weight)

Fast gradient boosting for clinical tabular data.

3. CatBoost

Handles categorical variables natively without extensive preprocessing.

4. SAINT / SAINT-B Transformer

A transformer architecture designed specifically for tabular data, with:

Embeddings for categorical & numerical features

Self-attention across patient features

Warmup scheduling

Early stopping

Class imbalance weighting

5. Stacked Meta-Ensemble


Combining XGBoost, CatBoost, LightGBM, and SAINT-B via a meta-learner.

📊 Results (Test Set)
Model	Threshold	Accuracy	Precision	Recall	F1 Score	AUC	Specificity
XGBoost (base)	0.50	0.79	0.6207	0.6429	0.6316	0.8284	0.8472
SAINT-B (base)	0.50	0.71	0.4889	0.7857	0.6027	0.8160	0.6806
CatBoost (base)	0.50	0.75	0.5556	0.5357	0.5455	0.7976	0.8333
LightGBM (base)	0.50	0.73	0.5152	0.6071	0.5574	0.7932	0.7778
Stacked Ensemble	0.50	0.77	0.6316	0.4286	0.5106	0.6917	0.9028
Key Findings

XGBoost achieved the best overall balance (AUC = 0.828).

SAINT-B achieved the highest recall, identifying more true "Dead" cases — important for clinical prioritization.

Stacked Ensemble improved specificity and stability across metrics.
