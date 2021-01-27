# Capstone-Azure-Machine-Learning-Engineer
This project aims at creating a machine learning customized model whose hyperparameters are tuned using HyperDrive for optimizing the pipeline and comparing the results obtained with the model constructed using Azure AutoML and deploy the best performing model. To build the pipeline we use Python SDK and a Scikit-learn model.

## Architecture
The project architecture involves the following major steps: 
script file : train.py
 * Import the dataset from the specified URL.
 * Obtain the Data.
 * Splitting the data into train and test datasets with 8:2 ratio of total available data respectively.

jupyter notebook:

* For customized model whose hyperparameters are tuned using HyperDrive
 * Creating a workspace for the pipeline.
 * Using CPU clusters if already existing or create new cluster.
 * I used Random sampling method for optimizing the hyperparameters 'C' and 'max_iter' using uniform and randint hyperdrive parameter expressions.
 * The early termination policy is BanditPolicy with an evaluation interval of 2 and slack_factor of 0.1.
 * The hyperdrive is configured using the SKLearn estimator, hyperparameter sampler, and policy.
 * Save the best model.
 * Once the run is finished I registered the best model obtained using HyperDrive.
* For AutoML model
 * we obtain a csv webfile dataset.
 * configure by setting the parameters of AutoMLConfig.
 * submit the AutoML run.
 * Obtain the metrics from the model.
 * Save the best model.
 
Compare the performance of both the models and then deploy the best model.
Once the model is deployed on the Azure Container Instance, test the model by providing sample input.
Get the log details and then delete the service. 

## Dataset
### Overview
I pass used the an open dataset from Kaggle Heart Failure Prediction
(https://www.kaggle.com/andrewmvd/heart-failure-clinical-data).
The dataset has 299 records of the patients.
### Task
 Heart failure is a common event caused by Cardiovascular diseases (CVDs) and this dataset contains 12 features that can be used to predict mortality by heart failure. 
### Access
The dataset is stored at

https://raw.githubusercontent.com/1AishwaryaSH/ML-Engineer-with-Azure-Capstone/main/heart_failure_clinical_records_dataset.csv

I imported the data into azure platform by uploading it from local files into Datasets for automated ML model whereas for tuning hyperparameters using hyperdrive I used the above mentioned link in the train.py file.

![](accuracyHyper.png)

![](after service.delete().png)

![](automlrun1.png)

![](automlrun2.png)

![](automlrun3.png)

![](automlrun4.png)

![](besthypermodel.png)

![](bestmodelauto.png)

![](bestmodelauto_azure.png)

![](cluster delete.png)

![](data1.png)

![](data2.png)

![](data3.png)

![](experiments.png)

![](instance delete.png)

![](metricsauto.png)

![](metricshyper.png)

 ![](rundHyper.png)

![]("/screenshots/rundauto.png")

![](webservice.png)

![](webservice2.png)
