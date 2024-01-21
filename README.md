# Thyroid-Cancer-Prediction-Model
## Thyroid Cancer Recurrence Prediction Project
## Table of Contents
I. Introduction

ii. Data Loading and Exploration

iii. Preprocessing

iv. Model Training

v. Model Optimization

vi. Model Evaluation

vii. Conclusion


### Introduction
This project aims to develop a machine learning model that can predict the recurrence of well-differentiated thyroid cancer. The model will be built using a dataset containing 13 clinicopathologic features collected over a span of 15 years. The dataset does not contain any missing values or sensitive data.

### Data Loading and Exploration
The first step in the project is to load the dataset into a pandas dataframe. The shape of the dataframe is (383, 17), indicating that there are 383 instances (patients) and 17 features. The features include 'Age', 'Gender', 'Smoking', 'Hx Smoking', 'Hx Radiothreapy', 'Thyroid Function', 'Physical Examination', 'Adenopathy', 'Pathology', 'Focality', 'Risk', 'T', 'N', 'M', 'Stage', 'Response', and 'Recurred'. There were 19 duplicate entries in the original dataset, which were dropped during the preprocessing stage.

### Preprocessing
The target variable 'Recurred' was converted to numerical form for model training. The 'No' and 'Yes' values were replaced with 0 and 1 respectively. This conversion is necessary because machine learning models work with numerical data.

## Model Training
The dataset was then split into features (X) and target variable (y). The features were further split into training set (x_train) and testing set (x_test), along with the corresponding target variables (y_train and y_test). The Random Forest Classifier was initialized with n_estimators=30, random_state=45, min_samples_split=6, and max_depth=6. The model was then trained on the training set.

### Model Optimization
To optimize the parameters of the Random Forest Classifier, RandomizedSearchCV was used. The parameter grid included different combinations of 'n_estimators', 'criterion', 'max_depth', and 'min_samples_split'. The cross-validation was done over 10 folds. The best model was found to have 'criterion'='entropy', 'max_depth'=12, 'min_samples_split'=9, and 'n_estimators'=2.

### Model Evaluation
The performance of the model was evaluated using the F1 score, precision, recall, and precision-recall curve. The model achieved an F1 score of 0.8985507246376813 on the test set, indicating that it performed well in terms of both precision and recall.

### Conclusion
In conclusion, this project successfully developed a machine learning model capable of predicting the recurrence of well-differentiated thyroid cancer. The model demonstrated good performance in terms of F1 score, indicating its effectiveness in distinguishing between patients likely to recur and those unlikely to. Future work could focus on refining the model further, incorporating additional data if available, and validating the model's performance in real-world clinical settings.
