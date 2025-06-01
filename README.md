
# Military_Models – Complete Retraining SVR Model (Approach 3)

**Model Scripts created in Python JupyterLab**  
**Author:** Ayden McCarthy  
**Manuscript Title:** *Optimisation of a Support Vector Regression Model Predicts Individuals’ Maximal Weight Lifted During a Simulated Military Manual Material Handling Assessment*  
**Program of Study:** PhD  
**Institution:** Macquarie University  
**Year:** 2025  

---

## 📘 Overview

This repository contains the finalized **Support Vector Regression (SVR)** model trained using the **complete retraining approach (Approach 3)**. The model was developed as part of a PhD thesis and is designed to predict maximal weight lifted during a simulated military manual material handling task. It includes:

- A Jupyter Notebook to **train** the complete model: `SVR_App_3.ipynb`
- A Jupyter Notebook to **predict** new cases using the trained model: `predict_complete_retrained_model.ipynb`
- The final model and scaler file: `svr_complete_retrained_model.joblib`

---

## 🧠 Model Summary

- **Model type:** Support Vector Regression (SVR)
- **Kernel:** Sigmoid
- **Training:** Fully retrained using mixed population data
- **Exported File:** `svr_complete_retrained_model.joblib`

This model file includes both the trained SVR estimator and the feature scaler (`StandardScaler`).

---

## 🗂️ Required Input Format

To generate predictions, the input CSV file must be named `new_data.csv` and include **all of the following columns** with exact header formatting:

- `IMTP_Peak Vertical Force [N]`  
- `Avg_Bicep`  
- `LCMJ_Velocity at Peak Power [m/s]`  
- `Concentric Peak Velocity [m/s]`  
- `Peak Power [W]`  
- `Sex`  
- `Height (cm)`  
- `Weight (kg)`  
- `Age`

> ❌ Do NOT include `Lift-to-Place` — this is the value the model predicts.

---

## ⚙️ How to Use in JupyterLab

1. Ensure the following files are in your working directory:
   - `svr_complete_retrained_model.joblib`
   - `new_data.csv`

2. Open and run:
   - `predict_complete_retrained_model.ipynb`

This notebook will:
- Automatically install required packages (`pandas`, `joblib`, etc.)
- Load the trained SVR model and scaler
- Preprocess your new input file
- Output predicted lift values

---

## 🧪 Output Example

```
Predicted Lift-to-Place value(s): [78.45 83.12 69.30]
```

---

## ⚙️ Environment Setup

To replicate the original setup:

```bash
pip install pandas joblib numpy scikit-learn matplotlib
```

Or let the prediction notebook install them automatically.

---

## 📜 License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute the code with attribution.

---

## 🙏 Citation

If using this model or code, please cite:

```
McCarthy, A. (2025). Optimisation of a Support Vector Regression Model Predicts Individuals’ Maximal Weight Lifted During a Simulated Military Manual Material Handling Assessment. PhD Thesis, Macquarie University.
```

---

## 🤝 Issues & Contributions

This repository distributes a finalized model for public use. For questions or improvements, please open an issue or submit a pull request.
