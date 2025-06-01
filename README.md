
# Military_Models

**Model Scripts created in Python JupyterLab**  
**Author:** Ayden McCarthy  
**Manuscript Title:** *Optimisation of a Support Vector Regression Model Predicts Individuals’ Maximal Weight Lifted During a Simulated Military Manual Material Handling Assessment*  
**Program of Study:** PhD  
**Institution:** Macquarie University  
**Year:** 2025  

---

## 📘 Overview

This repository contains Jupyter Notebook-based predictive models developed as part of a scientific research project. The focus of the models is to predict simulated military manual handling performance using machine learning approaches, specifically **Ridge Regression** and **Support Vector Regression (SVR)**. 

The notebooks are structured for transparency, reproducibility, and adaptability to other datasets in occupational and physical performance domains.

---

## 🧠 Model Suite

The key models provided include:

- `SVR_Approach_2.ipynb` – **Partial Retraining**: Fine-tunes a general population-trained model on mixed data.
- `SVR_App_3.ipynb` – **Complete Retraining**: Retrains the SVR model entirely using mixed data for maximal predictive alignment.

Each notebook includes:
- Data loading and preprocessing
- Model training and validation
- Performance evaluation
- Export functions for predictions

---

## 🗂️ Required Files

The following CSV files are required and must be placed in the working directory:

- `Training_Set_Gen_Pop_No_MP.csv`
- `Training_Set_Mil_Pop_No_MP.csv`
- `Testing_Set_Gen_Pop_No_MP.csv`
- `Testing_Set_Mil_Pop_No_MP.csv`

> These files are provided with correct column headers but contain no data—users must input their own datasets adhering to the required format.

---

## ⚙️ Environment Setup

To replicate the exact environment used for analysis:

1. **Clone the repository:**
   ```
   git clone https://github.com/AydenMQ/Military_Models.git
   cd Military_Models
   ```

2. **(Optional) Create a virtual environment:**
   ```
   python -m venv venv
   source venv/bin/activate  # Windows: venv\Scripts\activate
   ```

3. **Install required packages:**
   ```
   pip install -r requirements.txt
   ```

> These notebooks are intended to be run in **JupyterLab**. Make sure it is installed and launched via:
```
jupyter lab
```

---

## 📊 Usage Instructions

1. Ensure the required `.csv` files are prepared and placed in the project directory.
2. Open either `SVR_Approach_2.ipynb` or `SVR_App_3.ipynb` in JupyterLab.
3. Run each cell in sequence. Detailed comments guide the user through each step of preprocessing, model training, and evaluation.
4. Results (e.g., RMSE, predicted vs actual plots) will be generated inline and optionally saved.

---

## 📜 License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute the code with proper attribution.

---

## 🙏 Citation

If you use these models, code, or datasets for your own research or application, please cite:

```
McCarthy, A. (2025). Optimisation of a Support Vector Regression Model Predicts Individuals’ Maximal Weight Lifted During a Simulated Military Manual Material Handling Assessment. PhD Thesis, Macquarie University.
```

Or credit appropriately in your repository/documentation.

---

## 🤝 Contributions and Issues

Issues, feature requests, or suggestions are welcome via GitHub issues. Please open a pull request if you wish to contribute improvements to the notebooks or documentation.



# SVR Prediction Model (Partially and Completely Retrained)

This repository includes a partially retrained Support Vector Regression (SVR) model designed for predicting maximal weight lifted during a simulated military manual material handling task. The model can be executed independently using a pre-trained pipeline and external test data. This supports deployment scenarios where new assessments are evaluated using the optimized SVR.

The script `predict_svr_model.ipynb` allows users to load the saved model and generate predictions on custom input data using Python in Jupyter Lab. The prediction pipeline includes a `StandardScaler`, ensuring that all input features are scaled identically to the original training data.

## Inputs

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

## How to Use

1. Place the following files in the same working directory in your Jupyter Lab environment:
   - `svr_pipeline_model.joblib` (the saved model pipeline)
   - `new_data.csv` (your new input data with the columns listed above)

2. Open and run the notebook:
   - `predict_svr_model.ipynb`

This notebook will:
- Automatically install required packages (`pandas`, `joblib`) if not already installed
- Load the pre-trained SVR model pipeline
- Read and process the input CSV
- Output predictions directly in the notebook

## Output Example

```
Predictions: [78.45 83.12 69.30]
```

This setup ensures reproducibility and easy deployment of the SVR model for new military or general population assessments.
