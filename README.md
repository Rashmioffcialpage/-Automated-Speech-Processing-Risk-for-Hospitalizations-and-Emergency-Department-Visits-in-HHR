🎙️ Automatic Speech Recognition for Health Risk Detection
📌 Project Overview

This project implements an end-to-end automated speech processing and machine learning pipeline to identify potential health risks using acoustic features extracted from speech recordings. The goal is to explore whether speech can act as a non-invasive biomarker for early detection of health deterioration that may lead to hospitalization or emergency department visits, particularly in home healthcare settings.

The system is built using the Coswara COVID-19 speech dataset and focuses on binary classification between healthy individuals and those identified as positive or at-risk.

🎯 Motivation

In home healthcare, patients are not monitored continuously. Subtle health changes such as coughing patterns, breath control, and vocal fatigue may emerge between nurse visits and go unnoticed until the condition worsens.

Speech contains valuable acoustic cues related to respiratory and physiological health. This project investigates how machine learning and speech signal processing can be leveraged to detect early risk patterns using passive, low-cost, and scalable monitoring techniques.

🧠 Objectives

Design and implement a complete speech-based ML pipeline

Integrate audio features and metadata into a unified dataset

Extract clinically relevant acoustic features

Train and evaluate a binary classification model

Address class imbalance and prioritize minority-class detection

Analyze limitations and propose future extensions

📊 Dataset

Coswara COVID-19 Speech Dataset (Publicly Available)

Audio Modalities Used:

Heavy cough recordings

Deep breathing sounds

Sustained vowel phonation (/aaa/)

Short speech utterances

Dataset Statistics:
Metric	Value
Total samples	2,374
Usable samples	2,273
Healthy samples	1,794
Positive / At-Risk samples	479
Class imbalance	3.75 : 1
🔍 Problem Formulation

This is a binary classification problem:

Label 0 (Healthy):

healthy

recovered_full

no_resp_illness_exposed

Label 1 (Positive / At-Risk):

positive_mild

positive_asymptomatic

positive_moderate

A stratified 80/20 train-test split is used to preserve class distribution.

🎧 Feature Engineering

A total of 46 acoustic features were extracted, including:

MFCCs (39 features)

Static coefficients

Delta coefficients

Delta-delta coefficients

Spectral Features

Spectral centroid

Spectral bandwidth

Spectral rolloff

Zero-crossing rate

Temporal & Prosodic Features

Chroma features

Tempogram features (rhythm & pitch variation)

All features were standardized prior to model training.

🤖 Modeling Approach

Algorithm: XGBoost Classifier

Reason: Strong performance on structured data and non-linear feature interactions

Evaluation Metrics:

Accuracy

Precision

Recall

F1-score

ROC-AUC

Special emphasis was placed on positive-class recall, as missing at-risk patients is more critical than false positives in healthcare applications.

📈 Results (Baseline)

Accuracy: ~79%

AUC: ~0.70

Precision (Positive): ~0.65

Recall (Positive): ~0.42

These results highlight the impact of class imbalance and motivate further tuning and threshold optimization.

⚠️ Challenges

Class imbalance in healthcare data

Accuracy masking poor minority-class recall

Variability in recording quality

Single-dataset evaluation

🚀 Clinical Applicability & Future Work

Passive speech monitoring via smartphone applications

Early health-risk alerts between nurse visits

Integration of linguistic features from ASR systems

Validation on independent datasets

Longitudinal tracking of patient speech over time

Multimodal extensions combining speech with vitals

🧪 Technologies Used

Python

NumPy, Pandas

Scikit-learn

XGBoost

Matplotlib / Seaborn

Jupyter Notebook

📂 Repository Structure
├── ASR_FINAL_PROJECT.ipynb
├── ASR_Project_Report.pdf
├── Final_Presentation.pptx
├── README.md

👩‍💻 Authors

Rashmi

Ameerkhan

Course: Automatic Speech Recognition
Instructor: Dr. Kewei Isaac Li
Fall 2025

📜 License

This project is for academic and educational purposes only.
Dataset usage complies with Coswara’s public data license.
