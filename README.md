# Biological-and-Radiological-Dictionary-of-Radiomic-Features
"Paper Title: Biological and Radiological Dictionary of Radiomics Features: Addressing Understandable AI Issues in Personalized Prostate Cancer; Dictionary Version PM1.0".  

ArXiv: https://arxiv.org/abs/2412.10967

This study comprises two sections:
i) Development of a radiological/biological dictionary of radiomics features.
ii) Demonstration of the dictionary's practical application in addressing real-world problems, such as a classification task.


#i) Development of a radiological/biological dictionary of radiomics features.
The "Radiological and Biological Dictionary of Radiomics Features.xlsx" file contains four sheets:

1) Sheet name: Relationships_1 
Semantic Feature and Radiomics Feature Relationships: This sheet outlines the connections between semantic features and their corresponding radiomics features.

2) Sheet name: Radiomics Definitions_2 
Radiomics Feature Definitions: This sheet provides detailed definitions of various radiomics features.

3) Sheet name: PIRADS Definitions_3
PI-RADS Elements and Related Semantic Features: This sheet maps the PI-RADS elements to their associated semantic features.

4) Sheet name: Semantic Definitions_4 
Semantic Visual Assessment Criteria Definitions: This sheet offers definitions for the semantic criteria used in visual assessments.

   
#ii) Demonstration of the dictionary's practical application in addressing real-world problems, such as a classification task:
                     
                     Interpretable and Explainable Classification Task for Understandable AI Solutions                         
Strat of Classification Codes     
  =======================  

**Step 1: Automated Package Installation**

- **Input:**
 - List of required packages for the analysis.

- **Process:**
 - **1.1** Import necessary modules: `sys`, `subprocess`.
 - **1.2** Define the `install(package)` function to install missing packages using `pip`.
- **1.3** Create a list of required packages:
- `'skrebate'`, `'rulefit'`, `'scikit-learn'`, `'pandas'`, `'numpy'`, `'matplotlib'`, `'seaborn'`, `'xgboost'`, `'lightgbm'`, `'catboost'`.
- **1.4** Iterate through the list of required packages:
- Try to import each package using `__import__(package)`.
- If an `ImportError` occurs, print a message and call `install(package)` to install it.

  - **Output:**
    - All required packages are installed and available for use in the environment.

  ---

**Step 2: Importing Modules**

  - **Input:**
    - None (standard and third-party libraries).

  - **Process:**
    - **2.1** Import essential libraries for system operations and utility functions:
      - `os`, `shutil`, `inspect`, `datetime`.
    - **2.2** Import data manipulation and numerical computation libraries:
      - `pandas` as `pd`, `numpy` as `np`.
    - **2.3** Import visualization libraries:
      - `matplotlib.pyplot` as `plt`, `seaborn` as `sns`.
    - **2.4** Import scikit-learn modules for data preprocessing:
      - Imputers: `SimpleImputer`, `KNNImputer`, `IterativeImputer` (after enabling experimental features).
      - Scalers: `MinMaxScaler`, `StandardScaler`, `RobustScaler`, `Normalizer`, `MaxAbsScaler`.
    - **2.5** Import scikit-learn modules for model selection and evaluation:
      - `train_test_split`, `StratifiedKFold`, `GridSearchCV`, `RandomizedSearchCV`.
      - Metrics: `accuracy_score`, `precision_score`, `recall_score`, `f1_score`, `confusion_matrix`.
    - **2.6** Import feature selection methods:
      - `SelectKBest`, `chi2`, `f_classif`, `mutual_info_classif`.
    - **2.7** Import machine learning classifiers:
      - Linear models: `LogisticRegression`, `Lasso`.
      - Tree-based models: `DecisionTreeClassifier`, `RandomForestClassifier`.
      - Ensemble methods: `StackingClassifier`.
      - Support Vector Machine: `SVC`.
      - Neural Networks: `MLPClassifier`.
      - Discriminant Analysis: `LinearDiscriminantAnalysis`.
      - Nearest Neighbors: `KNeighborsClassifier`.
      - Naive Bayes: `GaussianNB`.
      - Gradient Boosting models: `XGBClassifier`, `LGBMClassifier`, `CatBoostClassifier`.
      - Rule-based model: `RuleFit`.
    - **2.8** Enable experimental features if necessary (e.g., `enable_iterative_imputer`).

  - **Output:**
    - All necessary libraries are imported and ready for use in the script.

  ---

     **Step 3: Parameters Configuration**

  - **Input:**
    - None (parameters are defined within the script).

  - **Process:**
    - **3.1 General Settings:**
      - **3.1.1** Set random seed for reproducibility:
        - `RANDOM_SEED = 11`.
      - **3.1.2** Define the number of top features to select:
        - `NOF = 5`.
      - **3.1.3** Set the number of folds for cross-validation:
        - `N_FOLDS = 5`.
      - **3.1.4** Define test size for train-test split:
        - `TEST_SIZE = 0.15` (i.e., 15% of data for testing).
    - **3.2 Classes Selection and Mapping:**
      - **3.2.1** Select specific classes to include:
        - `SELECTED_CLASSES = [0, 1, 2, 3, 4, 5]` (adjust as needed).
      - **3.2.2** Define class mapping to consolidate classes:
        - Map classes `0`, `1`, `2`, `3` to `0` (negative class).
        - Map classes `4`, `5` to `1` (positive class).
        - `CLASS_MAPPING = {0: 0, 1: 0, 2: 0, 3: 0, 4: 1, 5: 1}`.
    - **3.3 Class Selection Percentages:**
      - **3.3.1** Define the percentage of patients to select from each class before mapping:
        - `CLASS_SELECTION_PERCENT = {0: 1, 1: 1, 2: 1, 3: 1, 4: 1, 5: 1}` (100% selection for all classes).
    - **3.4 Data Paths:**
      - **3.4.1** Define the base directory for saving results:
        - `BASE_RESULTS_DIRECTORY = r'Add the path of the folder that you would like to store the results'`.
      - **3.4.2** Specify the file path for the input data:
        - `FILE_PATH = r'Add a excel file with .xlsx format'`.
      - **3.4.3** Set the sheet name for Excel files:
        - `SHEET_NAME = 0`.
    - **3.5 Imputation Strategy:**
      - **3.5.1** Specify the strategy for handling missing values:
        - `IMPUTATION_STRATEGY = 'SimpleImputer_mean'`.
    - **3.6 Scaling Method:**
      - **3.6.1** Specify the method for scaling features:
        - `SCALING_METHOD = 'MinMaxScaler'`.
    - **3.7 Feature Selectors:**
      - **3.7.1** Define feature selection methods and their parameters in `INVOLVED_FEATURE_SELECTORS`:
        - Examples include:
          - 'Chi-Square Test (CST)'
          - 'Correlation Coefficient (CC)'
          - 'Mutual Information (MI)'
          - 'Variance Threshold (VT)'
          - 'ANOVA F-test (AFT)'
          - 'Information Gain (IG)'
          - 'Univariate Feature Selection (UFS)'
          - 'Fisher Score (FS)'
          - 'LASSO'
    - **3.8 Classifiers:**
      - **3.8.1** Define classifiers, their initial parameters, and hyperparameter grids in `INVOLVED_CLASSIFIERS`:
        - Classifiers include:
          - **Decision Tree Classification (DTC)**
          - **Logistic Regression (LR)**
          - **Linear Discriminant Analysis (LDA)**
          - **Naive Bayes Classifier (NBC)**
          - **K-Nearest Neighbors (KNN)**
          - **Random Forest Classifier (RFC)**
          - **Support Vector Machine (SVM)**
          - **XGBoost Classifier**
          - **LightGBM Classifier**
          - **CatBoost Classifier**
          - **Stacking Classifier**
          - **MLP Classifier (MLP)**
          - **RuleFit Classifier (RUC)**
        - Each classifier has:
          - A model class.
          - Initial parameters (`params`).
          - A hyperparameter grid (`param_grid`) for tuning.
    - **3.9 Grid Search Configuration:**
      - **3.9.1** Set the grid search mode:
        - `GRID_SEARCH_MODE = 'randomized'`.
      - **3.9.2** Define the number of iterations for randomized search:
        - `GRID_SEARCH_ITER = 5`.

  - **Output:**
    - All configuration parameters are set and ready for use in the analysis.

  ---

     **Step 4: Data Reading, Shuffling, Class Selection, and Mapping**

  - **Input:**
    - The data file specified by `FILE_PATH` (supports `.xlsx`, `.xls`, `.csv` formats).

  - **Process:**
    - **4.1 Data Reading:**
      - **4.1.1** Read the data file using `pandas` based on the file extension.
        - If the file is Excel (`.xlsx`, `.xls`), use `pd.read_excel(FILE_PATH, sheet_name=SHEET_NAME)`.
        - If the file is CSV (`.csv`), use `pd.read_csv(FILE_PATH)`.
      - **4.1.2** Extract components from the data:
        - `Patient_ID`: The first column.
        - `Data`: All columns from the second to the second-to-last.
        - `Outcome`: The last column.
    - **4.2 Diagnostics Before Mapping:**
      - **4.2.1** Print unique values in `Outcome` before filtering and mapping.
      - **4.2.2** Check and print the number of missing values in `Outcome`.
    - **4.3 Data Filtering and Shuffling:**
      - **4.3.1** Filter the dataset to include only `SELECTED_CLASSES`.
        - Create a mask and apply it to the data.
      - **4.3.2** Shuffle the filtered data if necessary to ensure randomness.
      - **4.3.3** Update `Patient_ID`, `Data`, and `Outcome` after filtering and shuffling.
    - **4.4 Class Selection by Percentage:**
      - **4.4.1** Define a function `select_percentage_per_class` to select a specified percentage of patients from each class.
      - **4.4.2** Apply the function to select data as per `CLASS_SELECTION_PERCENT`.
      - **4.4.3** Update `Patient_ID`, `Data`, and `Outcome` after selection.
      - **4.4.4** Verify the selection by printing class distribution after selection.
    - **4.5 Class Mapping:**
      - **4.5.1** Map original classes to new classes using `CLASS_MAPPING`.
        - Use `Outcome_mapped = Outcome.map(CLASS_MAPPING)`.
      - **4.5.2** Ensure no missing values after mapping.
        - If missing values are found (unmapped classes), raise a `ValueError`.
      - **4.5.3** Update `Outcome` with the mapped classes.
    - **4.6 Feature Separation:**
      - **4.6.1** Identify numeric columns using `Data.select_dtypes(include=[np.number])`.
      - **4.6.2** Identify non-numeric columns using `Data.select_dtypes(exclude=[np.number])`.
      - **4.6.3** Separate numeric and non-numeric data.

  - **Output:**
    - Prepared `Patient_ID`, `Data`, and `Outcome` variables for further processing.

  ---

     **Step 5: Preprocessing**

  - **Input:**
    - `Data`, `Outcome`.

  - **Process:**
    - **5.1 Stratified Splitting:**
      - **5.1.1** Perform a stratified train-test split using `train_test_split` to maintain class distribution.
        - Split data into:
          - `X_train_num`, `X_test_num`: Numeric features.
          - `y_train`, `y_test`: Target variable.
          - `Patient_ID_train`, `Patient_ID_test`: Patient identifiers.
        - Parameters:
          - `test_size=TEST_SIZE`
          - `random_state=RANDOM_SEED`
          - `stratify=Outcome`
    - **5.2 Imputation:**
      - **5.2.1** Initialize the imputer based on `IMPUTATION_STRATEGY`.
        - For `'SimpleImputer_mean'`, use `SimpleImputer(strategy='mean')`.
      - **5.2.2** Fit the imputer on `X_train_num` and transform both training and testing data:
        - `X_train_num_imputed = imputer.fit_transform(X_train_num)`
        - `X_test_num_imputed = imputer.transform(X_test_num)`
    - **5.3 Scaling:**
      - **5.3.1** Initialize the scaler based on `SCALING_METHOD`.
        - For `'MinMaxScaler'`, use `MinMaxScaler()`.
      - **5.3.2** Fit the scaler on the imputed training data and transform both training and testing data:
        - `X_train_scaled = scaler.fit_transform(X_train_num_imputed)`
        - `X_test_scaled = scaler.transform(X_test_num_imputed)`

  - **Output:**
    - `X_train_scaled` and `X_test_scaled`: Preprocessed feature matrices ready for feature selection and modeling.

  ---

     **Step 6: Feature Selection**

  - **Input:**
    - `X_train_scaled`, `y_train`, feature selectors, `NOF`.

  - **Process:**
    - **6.1 Define Feature Selector Functions:**
      - Implement functions for each feature selection method:
        - **6.1.1** `apply_correlation_coefficient`:
          - Calculate the absolute correlation between each feature and the target.
          - Select the top `NOF` features with the highest correlation.
        - **6.1.2** `apply_chi_square`:
          - Use `SelectKBest` with `score_func=chi2` to select top `NOF` features.
        - **6.1.3** `apply_mutual_information`:
          - Use `SelectKBest` with `score_func=mutual_info_classif` to select top `NOF` features.
        - **6.1.4** `apply_variance_threshold`:
          - Calculate variance of each feature and select top `NOF` features with highest variance.
        - **6.1.5** `apply_anova_f_test`:
          - Use `SelectKBest` with `score_func=f_classif` to select top `NOF` features.
        - **6.1.6** `apply_information_gain`:
          - Equivalent to mutual information; use `apply_mutual_information`.
        - **6.1.7** `apply_univariate_feature_selection`:
          - Use `SelectKBest` with a specified `score_func` to select top `NOF` features.
        - **6.1.8** `apply_fisher_score`:
          - Manually compute Fisher Scores and select top `NOF` features.
        - **6.1.9** `apply_lasso`:
          - Use `Lasso` regression to select features with non-zero coefficients.
          - Adjust for cases where fewer than `NOF` features are selected.
    - **6.2 Map Functions:**
      - **6.2.1** Create a dictionary `feature_selector_functions` mapping function names to the actual functions.

  - **Output:**
    - Feature selector functions are ready to be applied.

  ---

     **Step 7: Applying Feature Selection and Classifiers**

  - **Input:**
    - Preprocessed data (`X_train_scaled`, `X_test_scaled`), `y_train`, `y_test`, `Patient_ID_train`, `Patient_ID_test`, feature selectors, classifiers, grid search configuration.

  - **Process:**
    - **7.1 Initialize Storage Structures:**
      - **7.1.1** Initialize lists and dictionaries to store results, selected features, confusion matrices, and best hyperparameters.
      - **7.1.2** Create a timestamped `results_directory` to store outputs.
      - **7.1.3** Create subdirectories:
        - `Predicted_Outcome/Fivefold Cross Validation`
        - `Predicted_Outcome/External Testing`
        - `Tuning_Hyperparameters`
    - **7.2 Initialize Stratified K-Fold:**
      - **7.2.1** Set up `StratifiedKFold` with `n_splits=N_FOLDS`, `shuffle=True`, `random_state=RANDOM_SEED`.
    - **7.3 Iterate Over Feature Selectors:**
      - For each feature selector in `feature_selectors`:
        - **7.3.1 Apply Feature Selection:**
          - **7.3.1.1** Retrieve the function and parameters from `INVOLVED_FEATURE_SELECTORS`.
          - **7.3.1.2** Apply the feature selection function to `X_train_scaled` and `y_train`.
          - **7.3.1.3** Obtain selected feature indices and names.
          - **7.3.1.4** Apply the same feature selection to `X_test_scaled`.
          - **7.3.1.5** Store selected features for later reference.
        - **7.3.2 Iterate Over Classifiers:**
          - For each classifier in `classifiers`:
            - **7.3.2.1 Hyperparameter Tuning:**
              - **7.3.2.1.1** Retrieve the model class, initial parameters, and hyperparameter grid from `INVOLVED_CLASSIFIERS`.
              - **7.3.2.1.2** Initialize the classifier with initial parameters.
              - **7.3.2.1.3** Use `RandomizedSearchCV` or `GridSearchCV` for hyperparameter tuning:
                - If `GRID_SEARCH_MODE == 'randomized'`, use `RandomizedSearchCV` with `n_iter=GRID_SEARCH_ITER`.
                - Handle cases where `param_grid` is a list (switch to `GridSearchCV`).
              - **7.3.2.1.4** Fit the search object on `X_train_selected` and `y_train`.
              - **7.3.2.1.5** Retrieve and store the best hyperparameters.
            - **7.3.2.2 K-Fold Cross-Validation:**
              - **7.3.2.2.1** Initialize metrics storage for each fold.
              - **7.3.2.2.2** For each fold in `StratifiedKFold`:
                - **7.3.2.2.2.1** Split `X_train_selected` and `y_train` into training and validation sets.
                - **7.3.2.2.2.2** Instantiate a new classifier with the best hyperparameters.
                - **7.3.2.2.2.3** Train the classifier on the training fold.
                - **7.3.2.2.2.4** Predict on the validation fold.
                - **7.3.2.2.2.5** Compute evaluation metrics: Accuracy, Precision, Recall, F1-Score.
                - **7.3.2.2.2.6** Store predictions, true labels, patient IDs, and fold numbers.
                - **7.3.2.2.2.7** Predict on the external test set.
                - **7.3.2.2.2.8** Compute test metrics and store predictions.
                - **7.3.2.2.2.9** Compute and store confusion matrices for both validation and test sets.
              - **7.3.2.2.3** Aggregate metrics across folds and compute means and standard deviations.
              - **7.3.2.2.4** Save cross-validation and test predictions to CSV files in their respective directories.
            - **7.3.2.3 Save Best Hyperparameters:**
              - **7.3.2.3.1** Save the best hyperparameters for the classifier to a CSV file in `Tuning_Hyperparameters`.
        - **7.3.3 Save Selected Features:**
          - **7.3.3.1** Save the list of selected features for the feature selector to `selected_features.csv`.

  - **Output:**
    - Results including evaluation metrics, selected features, confusion matrices, and best hyperparameters are collected and ready for saving.

 ---

 **Step 8: Saving and Aggregating Results**

 - **Input:**
   - Collected results from Step 7.

 - **Process:**
   - **8.1 Aggregate Metrics:**
     - **8.1.1** Concatenate results from all classifiers and feature selectors into a single DataFrame (`results_df`).
     - **8.1.2** Compute average metrics (mean and standard deviation) grouped by `Feature Selector` and `Classifier`:
      - Metrics include:
        - Validation and Test Accuracy
         - Precision
         - Recall
         - F1-Score
   - **8.2 Save Metrics:**
     - **8.2.1** Save detailed evaluation metrics to `evaluation_metrics.csv` in `results_directory`.
     - **8.2.2** Save average metrics to `average_metrics.csv`.
     - **8.2.3** Extract and save standard deviations to `STD_metrics.csv`.
   - **8.3 Save Confusion Matrices:**
     - **8.3.1** Save all confusion matrices to `confusion_matrices.csv`.
   - **8.4 Copy Original Data File:**
     - **8.4.1** Copy the original data file to the `results_directory` for reference.
  - **8.5 Save Workflow and Code:**
     - **8.5.1** Save the workflow description as `Workflow_Ver18.txt`.
     - **8.5.2** Save the script code as `Code_Ver18.py`:
       - Use `inspect.getsource` to retrieve the code.
     - Handle exceptions if `inspect` cannot retrieve the code.
  - **8.6 Save Best Hyperparameters:**
    - **8.6.1** Combine best hyperparameters from all classifiers and feature selectors.
    - **8.6.2** Save to `best_parameters.csv` in `Tuning_Hyperparameters`.

- **Output:**
   - All results are saved in the organized `results_directory`.

 ---

  **Step 9: Final Output Messages**

 - **Input:**
   - None.

 - **Process:**
   - **9.1** Print messages summarizing the completion of the script and locations of saved files:
     - Results files (evaluation metrics, average metrics, standard deviations).
     - Selected features.
     - Confusion matrices.
     - Predictions from cross-validation and testing.
     - Best hyperparameters.
     - Original data file.
     - Workflow description and code.
- **9.2** If no results are available, inform the user to check data and parameters.

 - **Output:**
- User is informed about the successful completion and where to find all outputs.

 =======================  
End of Classification Codes       
=======================  




