DIABETES DETECTION PROGRAM

1. PROJECT OVERVIEW:

This project implements a robust, optimized machine learning pipeline to predict the onset of Diabetes based on Pima Indians Diabetes Dataset.The system uses an Ensemble Learning Model (Random Forest) coupled with advanced preprocessing and hyperparameter tuning to ensure reliability.

The primary goal is to maximize the F1-Score, ensuring the model provides as balanced screening tool by minimizing both critical missed diagnoses (False Negatives) and costly false alarms (False Positives).



2. FEATURES:

The Program encapsulates three major functional modules:

* Data Processing & Cleaning:
   - FEATURE: Automated Pipeline
   - DESCRIPTION: Loads data, identifies illogical zero values (e.g., in Glucose, BMI) and replaces them with NaN. Uses a Pipeline to chain necessary imputation (SimpleImputer) and feature normalization (StandardScaler) steps safely.

* Prediction & Tuning:
   - FEATURE: Optimal Random Forest
   - DESCRIPTION: Trains a Random Forest Classifier whose hyperparameters are systematically optimized using GridSearchCV with 5-Fold Cross-Validation.

* Reporting & Validation:
   - FEATURE: Metrics & Analysis Functions
   - DESCRIPTION: Generates comprehensive output including Accuracy, F1-Score and AUC-ROC, followed by a granular breakdown of True/False Positives/Negatives from the confusion matrix.

3. Technologies & Tools Used:
   - Language: Python 3x
   - Data Handling: pandas, numpy 
   - Machine Learning (scikit-learn):
        * Model: RandomForestClassifier (Ensemble Model)
        * Tuning/Validation: GridSearchCV, Pipeline
        * Preprocessing: SimpleImputer, StandardScaler

4. SETUP & STEPS TO RUN:

a. PREREQUISITES:
   1. Ensure Python 3 is installed
   2. Install the required libraries:

      - pip install pandas numpy scikit-learn

b. DATA REQUIREMENT:
   1. Download the Pima Indians Diabetes Dataset (available on Kaggle or the UCI repository).
   2. Save the data file in the same directory as the Python script.
   3. Rename the file to pima_indians_diabetes_dataset.csv to avoid a FileNotFoundError.

c. EXECUTION:
Run the main python script from your terminal:

  - python diabetesdetectionprogram.py

The program will print a step-by-step workflow followed by the final evaluation metrics and then finally a detailed error analysis based on the confusion matrix values.

5. INSTRUCTIONS FOR TESTING AND VALIDATION:

The project employs a highly robust internal testing and validation approach to ensure reliable results:

a. DATA SPLIT: The dataset is split into 70% for training/tuning and 30% for independent testing (test_size = 0.3). All final metrics (Accuracy, F1, AUC_ROC) are calculated exclusively on this unseen 30% Test Set.

b. Model Validation (CV): The GridSearchCV module performs 5-Fold Cross-Validation (cv = 5) on the training data. This ensure the optimal hyperparameters found are reliable across different subsets of the training data, fulfilling the Reliability requirement.

c. Optimization Check: The model is optimized for the F1-Score (scoring = 'f1'). This verifies that the chosen model configuration provides best possible balance between identifying sick patients (Recall) and avoiding false alarms (Precision). The output analysis clearly details the resulting trade-off in the confusion matrix.

AUTHOR: NIHAL MUHAMMED
