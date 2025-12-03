# Parkinson's Disease Diagnosis from Voice using Random Forest and TensorFlow Lite

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.15870821.svg)](https://doi.org/10.5281/zenodo.15870821)   
[![DOI](https://zenodo.org/badge/1049031107.svg)](https://doi.org/10.5281/zenodo.17800494)   

## 📋 Project Overview

This project presents a machine learning system capable of diagnosing Parkinson's Disease through voice sample analysis. The model has been specifically developed and donated to **Cure Parkinson's** ([https://cureparkinsons.org.uk/](https://cureparkinsons.org.uk/)) to support their research efforts.

*Acknowledgement of the research donation from Cure Parkinson's Community & Events Officer, Tash Burrell.*
![Email Confirmation from Cure Parkinson's](./assets/Screenshot%202025-09-02%20134312.png)

## 🎯 Key Features

- **Voice-based Diagnosis**: Analyzes 22 distinct vocal features to detect Parkinson's Disease.
- **Random Forest Classifier**: Robust machine learning model with excellent performance metrics.
- **TensorFlow Lite Conversion**: Optimized for deployment on mobile and embedded devices for accessible diagnostic support.
- **Clinical Application**: Designed for real-world diagnostic scenarios.

## 📊 Dataset & Model Performance

- **Dataset**: 195 samples with 24 features (147 Parkinson's, 48 healthy).
- **Accuracy**: 92% overall.
- **Recall for Parkinson's class**: 97%.
- **AUC-ROC Score**: 0.96, indicating excellent model performance.
- **Confusion Matrix**: Only 3 errors out of 39 test samples.

### Detailed Metrics
| Class | Precision | Recall | F1-Score | Support |
| :---- | :-------: | :----: | :------: | :-----: |
| 0 (Healthy) | 0.89 | 0.80 | 0.84 | 10 |
| 1 (Parkinson's) | 0.93 | 0.97 | 0.95 | 29 |
| **Weighted Avg** | **0.92** | **0.92** | **0.92** | 39 |

## 🛠️ Technical Implementation

### Model Architecture
- **Algorithm**: Random Forest Classifier, chosen for its robustness with small/medium datasets and ability to handle imbalance.
- **Optimal Hyperparameters** (found via GridSearchCV):
  - `n_estimators`: 100
  - `max_depth`: None
  - `min_samples_split`: 5

### Feature Selection
The model uses 22 clinically relevant vocal features, including:
- Fundamental frequency characteristics (`MDVP:Fo(Hz)`, `MDVP:Fhi(Hz)`, `MDVP:Flo(Hz)`)
- Perturbation measures (`MDVP:Jitter(%)`, `MDVP:Jitter(Abs)`, `MDVP:RAP`, `MDVP:PPQ`, `Jitter:DDP`)
- Amplitude variation measures (`MDVP:Shimmer`, `MDVP:Shimmer(dB)`, `Shimmer:APQ3`, `Shimmer:APQ5`, `MDVP:APQ`, `Shimmer:DDA`)
- Noise/Harmonic ratios (`NHR`, `HNR`)
- Nonlinear complexity measures (`RPDE`, `DFA`, `spread1`, `spread2`, `D2`, `PPE`)

### TensorFlow Lite Conversion
- **Input shape**: `(None, 22)` (variable number of samples, each with 22 features).
- **Output**: Probability scores for both classes (e.g., `[0.0118, 0.9881]` → prediction for Class 1/Parkinson's).
- **Status**: Successfully converted and ready for integration into mobile or embedded applications.


## 🌟 Research Donation

This algorithm and the accompanying research have been officially donated to **Cure Parkinson's** for their ongoing research into Parkinson's Disease treatment and diagnosis. The donation was acknowledged by their Research Team as a valuable contribution to their work, as shown in the email correspondence.

![Email Confirmation from Cure Parkinson's](./assets/Screenshot%202025-09-02%20134312.png)
*Acknowledgement of the research donation from Cure Parkinson's Community & Events Officer, Tash Burrell.*

## 📄 Citation

This work is archived and protected by DOI via Zenodo. Please cite it as:

```bibtex
@software{rossi_angela_2024,
  title     = {Parkinson's Disease Diagnosis from Voice using Random Forest and TensorFlow Lite},
  author    = {Rossi, Angela},
  year      = {2024},
  month     = dec,
  publisher = {Zenodo},
  doi       = {10.5281/zenodo.15870821},
  url       = {https://doi.org/10.5281/zenodo.15870821}
}
