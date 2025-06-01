
# Military_Models – Complete Retraining SVR Model (Approach 3)

**Model Scripts created in Python JupyterLab**  
**Author:** Ayden McCarthy  
**Manuscript Title:** *Optimisation of a Support Vector Regression Model Predicts Individuals’ Maximal Weight Lifted During a Simulated Military Manual Material Handling Assessment*  
**Program of Study:** PhD  
**Institution:** Macquarie University  
**Year:** 2025  

---

## 📘 Overview

This repository contains the finalized **Support Vector Regression (SVR)** model developed using the **complete retraining approach (Approach 3)**. The model predicts maximal weight lifted during a simulated military manual material handling task. It was built using both general and military datasets and supports full model retraining, feature selection, evaluation, and deployment.

Included files:
- `SVR_App_3.ipynb` – Notebook to **train** and evaluate the model with SHAP analysis and SBS feature selection
- `predict_complete_retrained_model.ipynb` – Notebook to **predict** new cases using the saved model
- `svr_complete_retrained_model.joblib` – Saved model and scaler for reuse

---

## 🧠 Model Summary

- **Model:** Support Vector Regression (SVR)
- **Kernel:** Sigmoid (selected via GridSearchCV)
- **Feature Selection:** Sequential Backward Selection (SBS)
- **Evaluation:** Leave-One-Out Cross-Validation (LOO)
- **Explained with:** SHAP values

Saved model includes both the SVR regressor and the StandardScaler used for feature normalization.

---

## 🛠️ Training Instructions

To train and evaluate the complete retrained SVR model:

1. Place the following datasets in your working directory:
   - `Training_Set_Gen_Pop_No_MP.csv`
   - `Training_Set_Mil_Pop_No_MP.csv`

2. Open and run all cells in `SVR_App_3.ipynb`. This notebook performs:
   - Data loading and concatenation
   - Grid search with LOO CV to optimize SVR hyperparameters
   - Sequential backward feature selection (SBS)
   - SHAP analysis for model interpretability
   - Final model evaluation and prediction visualization
   

Optional test set evaluation with:
   - `Testing_Set_Gen_Pop_No_MP.csv`
   - `Testing_Set_Mil_Pop_No_MP.csv`

---

## 🗂️ Input Format for Prediction

For new predictions, prepare a CSV file named `new_data.csv` with the following columns:

- `IMTP_Peak Vertical Force [N]`  
- `Avg_Bicep`  
- `LCMJ_Velocity at Peak Power [m/s]`  
- `Concentric Peak Velocity [m/s]`  
- `Peak Power [W]`  
- `Sex`  
- `Height (cm)`  
- `Weight (kg)`  
- `Age`

> ⚠️ Do NOT include the target `Lift-to-Place`. This is the model output.

---

## 🔍 Prediction Workflow

To generate predictions on new data:

1. Place these in your working directory:
   - `svr_complete_retrained_model.joblib`
   - `new_data.csv`

2. Run the notebook:
   - `predict_complete_retrained_model.ipynb`

This script will:
- Auto-install any missing packages (`pandas`, `joblib`, etc.)
- Load the trained SVR model and associated scaler
- Apply scaling and generate predictions

Example Output:

```
Predicted Lift-to-Place value(s): [78.45 83.12 69.30]
```

---

## ⚙️ Environment Setup

To install required packages manually:

```bash
pip install pandas numpy scikit-learn matplotlib joblib shap mlxtend
```

Or let the notebooks install them automatically on first run.

---

## 📜 License

This project is licensed under the [MIT License](LICENSE). You are free to use, adapt, and redistribute the code with appropriate attribution.

---

## 🙏 Citation

If you use or refer to this model in your work, please cite:

```
McCarthy, A. (2025). Optimisation of a Support Vector Regression Model Predicts Individuals’ Maximal Weight Lifted During a Simulated Military Manual Material Handling Assessment. PhD Thesis, Macquarie University.
```

---

## 🤝 Issues & Contributions

Questions, improvements, and collaborations are welcome. Please open a GitHub issue or submit a pull request.
