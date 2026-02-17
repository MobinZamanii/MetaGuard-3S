# MetaGuard-2S
A **Hybrid Stacking Ensemble (XGBoost + Random Forest)** for Cancer Metastasis Prediction, featuring a **Probabilistic Safety-Net** to minimize clinical False Negatives.

**MetaGuard-2S** is an advanced clinical decision support framework designed to detect cancer metastasis in highly imbalanced datasets. By leveraging a two-layer hybrid stacking architecture and a probabilistic "Safety Net," this system significantly reduces life-threatening False Negatives while maintaining high sensitivity.

---

## 🌟 Key Innovations

### 1. Hybrid Stacking Architecture
MetaGuard-3S processes patient data through a **two-layer intelligent pipeline**:
* **Stage 1 (XGBoost):** Initial pattern recognition and probability scoring.
* **Stage 2 (Hybrid Random Forest):** Combines XGBoost probabilities with enriched clinical features and **Statistical Mapping (Group\_Met\_Rate)** to enhance high-risk detection.

> Note: Logistic Regression has been removed in the current version due to limited additional benefit.

### 2. Probabilistic Safety-Net (Uncertainty-Aware)
A **Human-in-the-loop protocol** flags borderline predictions for expert review.  
* **Review Zone:** $[T - \delta, T + \delta]$, where $T$ is the model threshold and $\delta$ is a tunable uncertainty margin (e.g., 0.10).  
* This ensures that potential false negatives are caught before clinical decisions.

---

### Clinical Impact of the Safety Net
* **193 Patients Rescued:** ~19% of previously missed metastasis cases were flagged for expert review.  
* **347 False Alarms Prevented:** Reducing unnecessary biopsies by ~33%, improving patient safety and resource efficiency.

> 🔬 **Ongoing Work:** Threshold optimization and uncertainty margin calibration are continuing to further improve sensitivity and clinical reliability.

---

## 📂 Dataset Availability
Access to the dataset was granted by the **National Cancer Institute (NCI)** for research purposes.  
Due to the **Data Use Agreement (DUA)**, raw data cannot be redistributed publicly. Interested researchers should request access through the official NCI portal.

---

## 🛠️ Project Structure

```text
├── data/               # (Simulated/Anonymized) Clinical datasets
├── models/             # Saved .pkl files for XGBoost and Hybrid RF
├── notebooks/          # MetaGuard_Final_Notebook.ipynb
└── images/             # Confusion matrices, performance plots, and Safety-Net visualizations
```
Developed with ❤️ for medical advancement by Mobin Zamani
