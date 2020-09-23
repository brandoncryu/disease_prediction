# disease_prediction

Here we will walk through which files are most important and the order in which they are used.  Unfortunately since the data cannot be provided without going through the request and training process first the files themselves cannot be run directly.

The first file to look at is “Generate Sample Patients”.  This file loads the core data, our patients, their demographic data, their hospitalization events, and their diagnoses.  This is also where some feature engineering is done to create comorbidities.

The second file is “Generate Lab Data”.  This is where the bulk of our features come from.  It includes all of the test result data for each of our patients.  We do data cleaning here, aggregation, imputation, and checks for multicollinearity.

The third files are “Training Models”.  “Training Models” shows our check with PCA as well as running Recursive Feature Elimination with Logistic, Random Forest, and XGBoost models for our current prediction data.  It also includes a run of RFE and XGBoost for our future predictive model.

There are also Male and Female specific files for each of the three above.  They perform the same tasks but are for our Male and Female specific models.

The final file is “Predict_Future”.  This file does all of the previous tasks, generate sample data, grab and clean lab data, and run models for our future predictive models.  It essentially follows the same steps as the other files but is streamlined specifically for the future models.
