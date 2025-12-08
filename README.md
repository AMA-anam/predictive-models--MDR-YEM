# predictive-models--MDR-YEM
MDR prediction in Yemen
Predictive Modeling of Multidrug-Resistant UTI Pathogens Using Machine Learning
📌 Overview
This repository contains the code and analytical framework for the research paper: "Predictive Modeling of Multidrug-Resistant UTI Pathogens Using Machine Learning: Insights from a Retrospective Study in Yemen."

The study develops and validates a diagnostic prediction model for Multidrug-Resistant (MDR) Urinary Tract Infections (UTIs) in resource-limited conflict zones. Using a retrospective cohort of 2,550 patient records from Sana'a, Yemen, we benchmarked six machine learning algorithms. The CatBoost model emerged as the optimal tool, offering a calibrated, interpretable solution to guide empirical antibiotic prescribing and support antimicrobial stewardship.

- Key Results:
- 
Best Model: CatBoost (Gradient Boosting)
Performance: AUC-ROC 0.832 | AUPRC 0.839 (Independent Test Set) 
Calibration: Excellent probabilistic reliability (ECE = 0.064) 
Interpretability: SHAP analysis identified Patient Age and Healthcare Setting as the dominant predictors of resistance.
Clinical Utility: Decision Curve Analysis (DCA) demonstrated superior net benefit over standard "Treat All" or "Treat None" strategies.

📂 Repository Structure
Bash

├── figures/                 # High-quality plots (ROC, SHAP, Calibration curves)
├── predictive_models.ipynb  # Main Jupyter Notebook containing the full analysis
├── requirements.txt         # List of dependencies (exact versions used in the study)
├── sample_data.csv          # Dummy dataset for testing code structure (Privacy Safe)
├── LICENSE                  # MIT License
└── README.md                # Project documentation
🛠️ Installation & Requirements
The analysis was performed in a Python 3.12 environment. To reproduce the results, install the required dependencies:

Bash

pip install -r requirements.txt
Key Libraries: catboost==1.2.8, xgboost==1.6.1, scikit-learn==1.5.0, shap==0.50.0, optuna==4.6.0, lightgbm==4.6.0.

💻 Usage Instructions
The core analysis is contained within predictive_models.ipynb. The workflow follows the 16-step framework detailed in the study:
Import Libraries: Setup of Python environment (Pandas, NumPy, Scikit-learn, etc.).
Data Splitting: Stratified split into Train (70%), Validation (15%), and Test (15%) sets.
Data Preprocessing: Cleaning, encoding, and scaling features.
Model Training (Train Set): Training candidate models (Logistic Regression, SVM, RF, XGBoost, LightGBM, CatBoost).
Model Evaluation (Validation Set): Initial performance comparison.
Threshold Optimization: Determining optimal probability cut-offs using Youden’s J statistic.
Model Re-evaluation: Assessing performance after applying optimized thresholds.
Best Model Selection: Ranking models via a weighted composite score (AUC, F1, Calibration).
Visual Comparison: Generating ROC, PR, and Calibration curves.
Model Persistence: Saving the optimal CatBoost artifact.
Final Evaluation (Test Set): Unbiased assessment on the independent hold-out set.
Comparative Analysis: Benchmarking CatBoost vs. Logistic Regression baseline.
Decision Curve Analysis (DCA): Quantifying net clinical benefit.
SHAP Analysis: Global and local feature interpretability.
LIME Analysis: Local explanations for individual predictions.
Subgroup Analysis: Assessing fairness across Age, Gender, and Sector subgroups.

To run the analysis:
Open predictive_models.ipynb in Jupyter Lab or Google Colab.
Ensure sample_data.csv (or your private dataset) is in the root directory.
Run all cells sequentially.

⚠️ Data Availability
Patient Privacy Note: The original clinical dataset used in this study contains sensitive patient information and is not publicly available to protect confidentiality. A sample_data.csv file containing dummy data with the exact same structure (columns and data types) is provided in this repository to demonstrate the code's functionality.

📜 License
This project is licensed under the MIT License - see the LICENSE file for details.

✉️ Contact
Corresponding Author: Abdulrahman Anam Email: abdulrahman.anam@su.edu.ye Affiliation: Faculty of Medicine and Health Sciences, Sana'a University, Yemen.

If you find this work useful for your research, please consider citing our paper.
