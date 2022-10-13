# Project: Operationalizing Machine Learning
This experiment contained information about a marketing campaign from a banking network. Information included age, marital status, default, loan information, and education. The bank is looking to predict the probability of a successful engagement with a client.

Using this data, an automated ML model was created and deployed using Azure Machine learning.  With this deployment a consumable endpoint was created that has monitoring and documentation capabilities.  Lastly, a pipeline was created to invoke the entire process with reusable and scalable code via the Azure SDK.

## Architectural Diagram
![arch_diag](images/architecture_diagram.png)
This diagram, provided via the Udacity course, gives an overview of the flow of activity taken. It highlights the dependencies that authentication has on the entire process.  Then AutoML was invoked to register the bank marketing data and find the  best classification model on the data.  Once the model is selected an endpoint is created to enable consumption as well as logging capabilities. In order to replicate these steps, a pipeline can be created to create a reusable code base.

## Key Steps
1. Authentication - User roles were established and verified for using Azure ML
2. Auto ML Model - Registered the bank marketing data and trained a classification model on it
![dataset_verification](images/dataset_verification.png)
![automl_success](images/automl_success.png)
3. Deploy Best Model - Auto ML selected the best model, which was then deployed in Azure ML
![top_model](images/top_model.png)
![service_status_and_update](images/service_status_and_update.png)
4. Enable Logging - Funcationality was enabled to check the model status and performance
![app_insight_jabber](images/app_insight_jabber.png)
5. Consome Model End Points - Data was fed to the model to check functionality
![endpoint_python_verification](images/endpoint_python_verification.png)
6. Create and Publish a Pipeline - A reusable code-driven approach to establishing an endpoint
![completed_pipeline](images/completed_pipeline.png)
![pipeline_dataset](images/pipeline_dataset.png)
![pipeline_overview](images/pipeline_overview.png)
![pipeline_run_details](images/pipeline_run_details.png)

## Screen Recording
Screen Recording Demonstration is located at:

