# med-specialty-classifier
This project implements a supervised classification model to predict the medical specialty of a consultation, using data such as patient age, sex, and year and month of the consultation. Several classification algorithms were compared, and Logistic Regression was selected as the final model due to its performance and simplicity.

# Classification of Medical Specialties with Machine Learning

## 🎯 Objective
The objective is to build a model that can predict the most likely medical specialty of a consultation, based on demographic and temporal characteristics. This can help in clinical resource optimization, demand analysis, and healthcare planning. 

## 📊 Dataset used The dataset contains medical consultation records with the following columns:
 `YEAR`: Year of the consultation - `MONTH`: Month of the consultation - `Sex`: Patient's sex - `Age`: Patient's age - `Specialty`: Medical specialty (target variable) >
 
## 📈 Performance metrics Evaluation of the final model (`LogisticRegression`) on the test set: 
- **Accuracy**: 16%
- **Macro F1**: 0.07
- **Weighted F1**: 0.16
- **Classes with the best performance**:
- Neonatology (F1 = 0.62)
-   Gynecology (F1 = 0.50) 
- Geriatrics (F1 = 0.24)
-  Pediatrics (F1 = 0.38) > Poor performance was observed in classes with few examples. It is recommended to group rare specialties to improve stability.
  
 ## ⚙️ Brief explanation of the pipeline 
The pipeline includes: 
1. **Preprocessing** with `ColumnTransformer`:
- Imputation of missing values ​​(`SimpleImputer`)
- Scaling of numeric variables (`StandardScaler`)
- Encoding of categorical variables (`OneHotEncoder`)
2. **Evaluated models**: - `LogisticRegression`
- `RandomForestClassifier` - `GradientBoostingClassifier` - `KNeighborsClassifier`
3. **Cross-validation** (`cross_validate`) with metrics: `f1_macro`, `accuracy`
4. **Fine-tuning** (`GridSearchCV`) for the finalist models
5. **Final evaluation** with `classification_report` and confusion matrix
