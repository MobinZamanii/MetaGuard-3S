# 🤖 Model Architecture & Specifications

This directory outlines the technical configuration of the **MetaGuard-3S** stacking ensemble. Our approach leverages the diverse learning biases of different algorithms to maximize sensitivity in metastasis detection.

## 🏗️ The Triple-Stage Architecture

### Stage 1: Gradient Boosting (XGBoost)
* **Role:** Primary non-linear pattern extractor.
* **Function:** Focused on capturing complex interactions between clinical features and the "Group_Met_Rate".
* **Optimization:** Tuned to prioritize Recall over Precision to ensure minimal initial misses.

### Stage 2: Ensemble Bagging (Random Forest)
* **Role:** Variance reducer and robust classifier.
* **Function:** Operates in parallel with Stage 1 to provide a stable decision boundary, mitigating the noise inherent in imbalanced medical data.

### Stage 3: Meta-Learner (Logistic Regression)
* **Role:** Probability Calibrator.
* **Function:** Instead of simple voting, this layer learns the optimal weights for Stage 1 and Stage 2 outputs.
* **Outcome:** Produces the final probability scores used for the **988 True Positive** detections.

## 🛡️ Decision Logic: The Safety Net
The models do not output a simple 0 or 1. We utilize the raw probability scores to implement our **Clinical Review Zone**:
* **Low Risk:** Probability < 0.416
* **Review Zone (Safety Net):** 0.416 ≤ Probability ≤ 0.616 (Where **186** patients were rescued).
* **High Risk:** Probability > 0.616

## 💾 Model Persistence
Due to GitHub's file size limits, the trained serialized models (`.pkl`) are stored externally. You can regenerate them by running the `MetaGuard_Full_Pipeline.ipynb` in the `notebooks/` directory.
