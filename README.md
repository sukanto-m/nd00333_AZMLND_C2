
# Operationalizing Machine Learning

In this project we use the Bank Marketing dataset to train machine learning models on AzureML for a classification task. Two approaches are used to operationalize: one is an AutoML run and the other is a pipeline run. The model with the highest accuracy rate is deployed as an endpoint as an Azure Container Instance (ACI). Through the ACI, the REST endpoint with authentication is used to access the model via API documentation enabled by Swagger.

## Architectural Diagram
![diagram](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/Images/MLOps-Flow.jpeg)

As the diagram shows, the dataset is loaded into the AutoML run as well as the pipeline through the Jupyter notebook as a registered dataset. It is then trained and deployed manually on the AutoML run and the same process is automated via the Python SDK in the Jupyter notebook. The pipeline enables us to automate the AutoML runs on a compute cluster and outputs a best model as well as a pipeline endpoint. The best model then gets deployed as an ACI endpoint. From our endpoint, we get API Documentation via Swagger, logging via Application Insight. At the end, users interact with our model through either the pipeline endpoint, or the ACI. They also interact with the API, logs, and performance metrics.

## Key Steps
*TODO*: Write a short discription of the key steps. Remeber to include all the screencasts required to demonstrate key steps. 

1. Ensure dataset is registered.

![dataset](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/Images/Screenshot%202021-08-15%20at%205.47.27%20PM.png)

2. AutoML run on compute cluster

![run](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/Images/Screenshot%202021-08-22%20at%206.02.33%20PM.png)

3. Best performing model

![model](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/Images/Screenshot%202021-08-21%20at%204.59.19%20PM.png)

4. Deploy the best model
![deploy](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/Images/Screenshot%202021-08-22%20at%206.43.38%20PM.png)

5. Enable logging and view logs

![logs](https://github.com/sukanto-m/nd00333_AZMLND_C2/blob/master/Images/Screenshot%202021-08-22%20at%206.41.52%20PM.png)

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
