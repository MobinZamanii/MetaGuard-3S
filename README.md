# MetaGuard-3S
A Triple-Stage Stacking Ensemble (XGBoost, RF, LR) for Cancer Metastasis Prediction featuring a Probabilistic Safety-Net to minimize clinical False Negatives.


**MetaGuard-3S** is an advanced clinical decision support framework designed to detect cancer metastasis in high-imbalance datasets. By utilizing a unique three-layer stacking architecture and a probabilistic "Safety Net," this system significantly reduces life-threatening False Negatives.

## 🌟 Key Innovations

### 1. Triple-Stage Stacking Architecture
Unlike standard models, MetaGuard-3S processes data through three intelligent layers:
* **Stage 1 (Boosting):** Initial pattern recognition using **XGBoost**.
* **Stage 2 (Hybridization):** Integrating clinical features with **Statistical Mapping (Group_Met_Rate)** via Random Forest.
* **Stage 3 (Meta-Learning):** Final calibration using **Logistic Regression** to harmonize predictions.

### 2. Probabilistic Safety Net (Uncertainty-Aware)
We implemented a "Human-in-the-loop" protocol by defining a **Review Zone (0.416 - 0.616)**. This allows the system to flag borderline cases for manual expert review, effectively catching patients that AI might otherwise miss.

## 📊 Performance Evolution

Our methodology achieved a significant leap in diagnostic sensitivity:

| Model Version | True Positives (Caught) | False Negatives (Missed) | Accuracy |
| :--- | :---: | :---: | :---: |
| **Hybrid Stage 2** | 907 | 593 | **89%** |
| **Final MetaGuard-3S** | **988** | **512** | 86% |

### Clinical Impact of the Safety Net:
* **186 Patients Rescued:** 36.3% of previously missed cases (False Negatives) were successfully recovered through the Uncertainty Zone.
* **1,756 False Alarms Prevented:** Reducing unnecessary biopsies and patient anxiety by 32.8%.

## Dataset Availability
Access to the dataset was formally granted by the National Cancer Institute (NCI) for research purposes. Due to the Data Use Agreement (DUA), the raw data cannot be publicly redistributed. Researchers interested in the data should apply for access directly through the official NCI portal.

## 🛠️ Project Structure
```text
├── data/               # (Simulated/Anonymized) Clinical datasets
├── models/             # Saved .pkl files for each stage
├── notebooks/          # MetaGuard_Final_Notebook.ipynb
└── images/             # Confusion matrices and performance plots

Developed with ❤️ for Medical Advancement by Mobin Zamani
