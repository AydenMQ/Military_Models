# Military_Models
Model Scripts created in Python Jupyter's Lab.
Code produced by Ayden McCarthy.
Manuscript Title: "Optimisation of a Support Vector Regression Model Predicts Individuals’ Maximal Weight Lifted During a Simulated Military Manual Material Handling Assessment".
Program of Study: PhD.
Institution: Macquarie University.
Year: 2025.
# Model Suite

This repository contains Jupyter Notebook models developed as part of a scientific manuscript. Each model is designed to predict a simulated military assessment outcome using either a ridge regression or a support vector regression. Each notebook follows a logical order and structure, providing reproducible and transparent data analysis for researchers and practitioners. This suite supports applications in performance modelling, prediction, and cross-validation for various populations.
# Environment Setup

To replicate the exact environment used in this project, please use the provided `requirements.txt` file:

## 🔧 How to Install:
1. Clone this repository:
   ```bash
   git clone https://github.com/AydenMQ/Military_Models.git
   cd Military_Models
   ```
2. Create a virtual environment (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. Install all required packages:
   ```bash
   pip install -r requirements.txt
   ```

This will ensure consistent package versions for reproducibility.


## SVR Prediction Model (Partially and Completely Retrained)

This repository includes a partially retrained Support Vector Regression (SVR) model designed for predicting maximal weight lifted during a simulated military manual material handling task. The model can be executed independently using a pre-trained pipeline and external test data. This supports deployment scenarios where new assessments are evaluated using the optimized SVR.

The script `predict_svr_model.ipynb` or `predict_svr_model.py` allows users to load the saved model and generate predictions on custom input data. The prediction pipeline includes a `StandardScaler`, ensuring that all input features are scaled identically to the original training data.

### Inputs

The required input file, `new_data.csv`, must contain the following predictor variables (column names must match exactly):

- IMTP_Peak Vertical Force [N]  
- Avg_Bicep  
- LCMJ_Velocity at Peak Power [m/s]  
- Concentric Peak Velocity [m/s]  
- Peak Power [W]  
- Sex  
- Height (cm)  
- Weight (kg)  
- Age  

**Note**: Do not include the target column `Lift-to-Place` in this file, as it is the variable the model will predict.

### How to Use

1. Place the following files in the same working directory:
   - `svr_pipeline_model.joblib` (the saved model pipeline)
   - `new_data.csv` (your new input data with the columns listed above)

2. Run the script using Python (in terminal or command line):
   ```bash
   python predict_svr_model.py
