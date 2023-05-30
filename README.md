# a-dynamic-risk-assessment-system
This is the final project of Machine Learning DevOps Engineer Nanodegree Program.

## Project Overview 
This project represents the final of the Udacity ML DevOps Engineer Nanodegree. It encompasses the complete process of deploying a machine learning model, including continuous data ingestion and monitoring for model drift, which influences decisions regarding retraining and redeployment. The deployed model is accessible through an API with multiple endpoints, allowing for inference as well as providing various statistics on model performance, data insights, and overall pipeline health.

The objective of this project is to develop a classifier that predicts customer churn and provides an overall risk assessment. Synthetic datasets are provided for training and simulating continuous operations. The project focuses on the implementation of MLOps components, prioritizing their effectiveness rather than the quality of the model itself

## Project Workflow
The workflow is broken down into the following components which are all separated:

- data ingestion
- model training (logisticRegression sklearn model for binary classification)
- model scoring
- deployment of pipeline artifacts into production
- model monitoring, reporting and statistics - API set-up for ML diagnostics and results
- process automation with data ingestion and model drift detection using CRON job
- retraining / redeployment in case of model drift

## How to use
The model API should be launched before executing project components. This can be achieved by running app.py script instantiating multiple project API endpoints including inference capability. Other components of the project include:

- ingestion.py to ingest data and prepare model training
- training.py to train a logisticregression model
- scoring.py to score the model in production against a test dataset
- deployment.py to deploy key artifacts to production (in particular the trained model artifact)
- diagnostics.py gather various analysis and diagnostics
- apicalls.py calls all diagnostics through the API and generate a consolidated report
- reporting.py allows to generate a full pdf report gathering performance plots, metrics and other useful statistics
- fullprocess.py should be run regularly using a CRON job. It monitors new data availability, checks model drift, decides to retrain and redeploy an updated model in case shifting is detected.