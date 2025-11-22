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
