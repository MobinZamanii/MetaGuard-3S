# 📊 Experimental Results & Clinical Validation

This directory contains the visual and quantitative evidence of the **MetaGuard-3S** performance.

## 📈 Performance Evolution
We tracked the model's improvement across different development phases:

### Phase 1: Hybrid Stage (XGB + RF + StatMap)
* **Status:** High Sensitivity, but significant False Negatives.
* **Key Metric:** Identified **907** Metastasis cases.
* **Visual:** `results/plots/confusion_matrix_hybrid.png`

### Phase 2: Final Stacking (MetaGuard-3S)
* **Status:** Optimized for clinical reliability.
* **Key Metric:** Identified **988** Metastasis cases.
* **Visual:** `results/plots/confusion_matrix_final.png`

## 🛡️ Safety Net Impact
The most critical result of this study is the **Uncertainty-Aware triage**.
* **Rescued Patients:** **186** individuals who were initially missed by the AI but caught in the 0.416 - 0.616 probability zone.
* **Efficiency:** Prevented **1,756** unnecessary diagnostic procedures.

---
*Note: All plots were generated using Seaborn and Matplotlib within the main pipeline notebook.*
