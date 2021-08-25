
# Operationalizing Machine Learning

In this project we use the Bank Marketing dataset to train machine learning models on AzureML for a classification task. Two approaches are used to operationalize: one is an AutoML run and the other is a pipeline run. The model with the highest accuracy rate is deployed as an endpoint as an Azure Container Instance (ACI). Through the ACI, the REST endpoint with authentication is used to access the model via API documentation enabled by Swagger.

## Architectural Diagram
![diagram](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/Images/MLOps-Flow.jpeg)

As the diagram shows, the dataset is loaded into the AutoML run as well as the pipeline through the Jupyter notebook as a registered dataset. It is then trained and deployed manually on the AutoML run and the same process is automated via the Python SDK in the Jupyter notebook. The pipeline enables us to automate the AutoML runs on a compute cluster and outputs a best model as well as a pipeline endpoint. The best model then gets deployed as an ACI endpoint. From our endpoint, we get API Documentation via Swagger, logging via Application Insight. At the end, users interact with our model through either the pipeline endpoint, or the ACI. They also interact with the API, logs, and performance metrics.

## Key Steps 

## 1. Upload and Register Dataset 
The first step is to upload the [Bank Marketing dataset](https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv) and register it on the ML Studio

![dataset](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/new_images/Screenshot%202021-08-25%20at%207.47.06%20AM.png)


## 2. AutoML run on compute cluster

In the next step, the automated ML run is initiated by configuring a compute cluster and selecting the uploaded dataset for the experiment. The completed experiment goes through some iterations and outputs a best model.

![run](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/new_images/Screenshot%202021-08-25%20at%208.19.46%20AM.png)

## 3. Best performing model

The best model is a collection of classifiers - Voting Ensemble - with an accuracy of nearly 92%.

![model](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/new_images/Screenshot%202021-08-25%20at%208.35.46%20AM.png)

## 4. Deploy the best model

We now proceed to deploy the best model as an Azure Container Instance with authentication enabled.

![deploy](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/new_images/Screenshot%202021-08-25%20at%209.07.37%20AM.png)


## 5. Enable logging and view logs

The deployed model is updated to enable logging of application insights. The logs can be viewed by running the logs.py script.

![logs](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/new_images/Screenshot%202021-08-25%20at%209.07.47%20AM.png)
![logging](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/new_images/Screenshot%202021-08-25%20at%209.32.21%20AM.png)


6. API of deployed model via Swagger and consuming the API via JSON input and output

![swagger](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/Images/Screenshot%202021-08-22%20at%207.11.26%20PM.png)

![API](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/Images/Screenshot%202021-08-22%20at%207.16.38%20PM.png)


7. Pipeline run via Jupyter notebook

![notebook](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/Images/Screenshot%202021-08-22%20at%207.33.12%20PM.png)

8. Dataset as AutoML module in Pipeline run

![data](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/Images/Screenshot%202021-08-22%20at%207.43.11%20PM.png)

9. View run on RunDetails widget

![view](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/Images/Screenshot%202021-08-22%20at%208.02.55%20PM.png)
![run](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/Images/Screenshot%202021-08-22%20at%208.03.08%20PM.png)

10. Publish pipeline and deploy as endpoint

![1](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/Images/Screenshot%202021-08-22%20at%208.05.22%20PM.png)



## Screen Recording


Link to screencast: https://www.youtube.com/watch?v=zfPPQMXPEbs&ab_channel=SukantoMukherjee

# Suggestions on improving the project

The dataset shows a class imbalance during the run so that can be addressed by better sampling, since a model performs only as well as its data. Metrics other than accuracy can also be used to improve the model performance.
