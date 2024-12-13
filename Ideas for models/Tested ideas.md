# Ideas for Models
This section outlines the various preprocessing techniques, feature engineering strategies, model assessments, and optimizations we considered during the development of our machine learning model. Each approach was tested and iterated upon in various models to determine the best-performing pipeline.

## 1. Preprocessing Techniques 🔧
### Treating Incoherences
- Approach 1: Remove all incoherences (tested in Model 1)
- Approach 2: Replace incoherences with missing values (tested in Models 2 and 3)
- Approach 3: Combine incoherence removal with replacing incoherences with missing values (tested in subsequent models)

### Handling Outliers 📊
- Approach 1: No removal of outliers (tested in Models 1, 2, and 3)
- Approach 2: Use an IQR-based approach to detect and remove outliers (tested in Model 4)
- Approach 3: Combine IQR-based removal with the exclusion of extreme outliers (tested in later models)

### Additional Row-wise Transformations 🔄
- Approach 1: No transformations (used in the majority of models)
- Approach 2: Replace 'U' with 'N' in the "Alternative Dispute Resolution" feature (tested in the final model)
- Approach 3: Aggregate certain categories (e.g., '5C. SPECIAL FUND - POI CARRIER WCB MENANDS' and '5A. SPECIAL FUND - CONS. COMM. (SECT. 25-A)') into an 'Other' category (tested in the final model)
- Approach 4: Replace 'X' and 'U' in the Gender feature with missing values

### Handling Missing Values ❓
- Approach 1: Impute missing values with means and modes (tested in Model 1)
- Approach 2: Impute using Decision Tree Regressor (tested in Models 2 and 4)
- Approach 3: Impute using KNN Imputer (tested in Model 3)
- Approach 4: Use conditional means and modes for imputation (tested in subsequent models)
- Approach 5: Impute missing values in "Accident Date" and "Birth Year" using KNN Imputer (tested in later models)

## 2. Feature Engineering 🛠️

### Encoding Strategies 🧮
- Approach 1: Proportionate Encoding (used in Models 1 to 5)
- Approach 2: One-Hot Encoding for low cardinality features (tested in Models 6 and 7)
- Approach 3: Frequency Encoding (using CountEncoder) for categorical features (used in the remaining models)

### Feature Selection Methods 🔍
- Approach 1: Check variance, Spearman coefficient, Recursive Feature Elimination (RFE), and Lasso (tested in all models)
- Approach 2: Use Feature Importance from a Regression Tree (applied in Models 4 to 8)
- Approach 3: Use Feature Importance from a Decision Tree (tested in Model 8)

## 3. Model Assessment ⚙️
The following models were assessed to identify the most effective algorithm:

- Logistic Regression (tested in all models)
- Decision Tree (tested in all models)
- Random Forest (tested in all models)
- Extreme Gradient Boosting (XGBoost) (tested from Model 4)
- Multilayer Perceptron (MLP) (tested from Model 6)
- Gaussian Naive Bayes (tested from Model 7)
- K-Nearest Neighbors (KNN) (tested in Model 8)

## 4. Model Optimization 🚀
We used different optimization techniques to fine-tune the models for better performance:

- Optuna with Random Search: For model hyperparameter optimization (tested in Model 5)
- GridSearch: For fine-tuning hyperparameters (applied from Model 8 onwards)
