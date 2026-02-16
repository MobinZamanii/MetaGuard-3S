# 📓 Comprehensive Model Pipeline

This directory contains the core implementation of the **MetaGuard-3S** framework in a single, streamlined Jupyter Notebook. This ensures full reproducibility and a seamless narrative of the research process.

## 🚀 The End-to-End Workflow

The notebook is meticulously organized into sequential sections, reflecting the complete development lifecycle:

### Phase 1: Data Profiling & Imbalance Analysis
* Detailed exploration of the **NCI dataset**, focusing on the severe class imbalance (1,500 vs 41,000 cases).
* Statistical visualization of feature distributions and target correlations.

### Phase 2: Implementation of "StatMap" Feature Engineering
* Implementation of the **Statistical Mapping (Group_Met_Rate)** technique to encode regional metastasis patterns.
* Real-time validation of feature importance after engineering.

### Phase 3: Triple-Stage Stacking Architecture
* **Stage 1 (XGBoost) & Stage 2 (Random Forest):** Training parallel base learners.
* **Stage 4 (Logistic Regression):** Meta-learning integration to produce the final calibrated probability scores.
* **Result Achievement:** The final pipeline reaches the benchmark of **988 True Positives**.

### Phase 4: Clinical Safety-Net & Error Mitigation
* Post-prediction analysis to define the **Uncertainty Zone (0.416 - 0.616)**.
* Formal calculation of the "Rescued Patients" metric, catching **186 False Negatives** for expert review.

---

## 📄 File Description
- **`MetaGuard_Full_Pipeline.ipynb`**: The primary notebook containing the entire code, from preprocessing to the final safety-net analysis.

## 🛠️ Instructions
1. Refer to the root `requirements.txt` for necessary libraries.
2. The notebook is documented with detailed Markdown cells to explain the clinical and mathematical rationale for each step.
