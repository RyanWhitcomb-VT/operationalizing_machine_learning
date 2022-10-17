# Project: Operationalizing Machine Learning
This experiment contained information about a marketing campaign from a banking network. Information included age, marital status, default, loan information, and education. The bank is looking to predict the probability of a successful engagement with a client.

Using this data, an automated ML model was created and deployed using Azure Machine learning.  With this deployment a consumable endpoint was created that has monitoring and documentation capabilities.  Lastly, a pipeline was created to invoke the entire process with reusable and scalable code via the Azure SDK.

## Architectural Diagram
![arch_diag](images/architecture_diagram.png)
This diagram, provided via the Udacity course, gives an overview of the flow of activity taken. It highlights the dependencies that authentication has on the entire process.  Then AutoML was invoked to register the bank marketing data and find the  best classification model on the data.  Once the model is selected an endpoint is created to enable consumption as well as logging capabilities. In order to replicate these steps, a pipeline can be created to create a reusable code base.

## Key Steps
1. Authentication - User roles were established and verified for using Azure ML
2. Auto ML Model - Registered the bank marketing data and trained a classification model on it
First the data was uploaded as a dataset for easy consumption within AutoML.
![dataset_verification](images/dataset_verification.png)

Then it was able to run a classification approach on the registered data.
![automl_success](images/automl_success.png)
3. Deploy Best Model - Auto ML selected the best model, which was then deployed in Azure ML
Once the automl was run, you can extract the best model run.
![top_model](images/top_model.png)
Then the model was deployed for consumption by other applications.  However, application insights is being depreciated, and the ability to turn that on in V2 Azure is not possible anymore.  As a workaround, the Azure portal provides many direct ways to monitor the model performance and traffic over time.  Additionally, the logs can be retrieved as well.
![service_status_and_update](images/service_status_and_update.png)
4. Enable Logging - Funcationality was enabled to check the model status and performance
The logging information shown above can also be executed as a python file
![logs_python](images/logs_python.png)
Jabber funcationality was not working in the V2 workspace.  The Azure portal allows other alternatives to going outside of the Azure ecosystem for monitoring and documentation.
![app_insight_jabber](images/app_insight_jabber.png)
#### To be clear, Application Insight is able to be enabled on the version of the workspace I am on, here is the status after the above error.
![app_insights_fail](images/app_insights_fail.png)
5. Consome Model End Points - Data was fed to the model to check functionality
The model endpoints were tested for proper funcionality.  This can also be done manually through the UI.
![endpoint_python_verification](images/endpoint_python_verification.png)
6. Create and Publish a Pipeline - A reusable code-driven approach to establishing an endpoint
A pipeline can repeat all the above steps using repeatable and savable code.
![completed_pipeline](images/completed_pipeline.png)
The pipeline can register data.
![automl_data](images/automl_data.png)
![pipeline_dataset_2](images/pipeline_dataset_2.png)
The pipeline can create endpoints for models.
![pipeline_overview](images/pipeline_overview.png)
Lastly, there is meta information about the pipeline performance itself, which is useful in a production setting.
![pipeline_run_details](images/pipeline_run_details.png)
Pipeline status images
![pipeline_status_1](images/pipeline_status_1.png)
![pipeline_status_2](images/pipeline_status_2.png)

## Screen Recording
Screen Recording Demonstration is located at: https://vimeo.com/759929080

## Standout Suggestions
When training the automl model, an additional feature creation step can be made.  Instead of just taking the raw values for modeling, doing a feature creation step by normalizing data, categorizing ages, or removing unnecessary features such as day of week can improve model accuracy.

For deploying the model, I found that deploying locally helped me debug some issues I was having with the deployment json file.  This is a good step that can be added in the production process.
