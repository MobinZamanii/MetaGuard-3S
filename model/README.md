# Models Folder

Contains the trained **MetaGuard-3S** models for cancer metastasis prediction.

## Files
- `hybrid_rf_final.pkl` – Final Hybrid Random Forest model with Group_Met_Rate feature.
- `best_threshold.pkl` – Decision threshold for achieving target recall.

## Usage
```python
import joblib

model = joblib.load("hybrid_rf_final.pkl")
threshold = joblib.load("best_threshold.pkl")

y_proba = model.predict_proba(X_new)[:, 1]
y_pred = (y_proba >= threshold).astype(int)
```
