# DEATH PREDICT - REPORT
### introduction
We aim to predict if a patient will die from heart failure(HF) while they are in intensive care unit (ICU).
For that we use the patient's different constant like 'age', 'diabetes', 'calcium in blood' and many others (48 of them).


### The data
The dataset is composed of 1172 patients with for each up to 50 parameter in a csv file. 
Each row represents a patient, each column represents a paramater. The parameter can be either discrete or numerical but can't be a sentence. 
Some patient have NaN value in some parameters

#### origin
The dataset come from the database MIMIC-III(US) the patient were admitted at Beth-Israel deaconess medical center between 2001 and 2012. The final dataset was published in september 2021.


### Data cleaning
The first problem : Replacing the NaN value, what we did there is to replaced NaN value with the average of the column (other people value's)

### Data preprocessing
We used a standart scaler to normalise all the dataset.
We wanted to --embed-- the data before using.

### Training
We split the data in two different set, the training set and the test set for that we used the "train_test_split" function which can be found in the "sklearn.model_selection" library
In a second time, we use a decision tree which improved by far our results.

### What other people did
"Patients meeting the inclusion criteria were identified from the MIMIC-III database and randomly divided into derivation and validation groups.
Independent risk factors for in-hospital mortality were screened using XGBoost and LASSO regression models in the derivation sample. 
Multivariable logistic regression analysis was used to build prediction models. 
Discrimination, calibration, and clinical usefulness of the predicting model were assessed using the C-index, calibration plot, and decision curve analysis. 
After pairwise comparison, the best performing model was chosen to build a nomogram according to the regression coefficients."
- Prediction model of in-hospital mortality in intensive care unit patients with heart failure: machine learning-based, retrospective analysis of the MIMIC-III database

### Result 
The first method used was MLP we had a 40% accuracy using it. After that, we went for a decision tree and we managed to reach around 80% accuracy.
Indeed, the decision trees are more efficient with tabular data. 
