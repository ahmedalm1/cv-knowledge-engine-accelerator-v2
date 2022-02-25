# Deployemnt Process
Deploying the accelerator can be done in seven simple steps, that cover every aspect from deploying the resources, creating the search service elements, and connecting to the index to the website and dashboard interfaces. 

## Prerequisites
In order to deploy the accelerator, clone or download this repository, and make sure the following requirements are met:
- Azure Subscription  
- Visual Studio 2019 or later
- VS Code - with Azure Functions extension
- Postman 
- Sample CV documents 

## Step 0: Deploy the resources
Using the provided ARM template, create all the required Azure resources by clicking on this button: 

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fahmedalm1%2Fcv-knowledge-engine-accelerator-v2%2Fmain%2FDeployment%2FAssets%2FARM%2520Template%2Ftemplate.json)

## Step 1: Setup the Environemnt 
After deploying the resources successfully, navigate to the newly created Storage Account in Azure, and upload the sample documents in a new blob container.

The sample documents can be found in [Assets/Sample CVs](https://github.com/ahmedalm1/cv-knowledge-engine-accelerator-v2/tree/main/Deployment/Assets/Sample%20CVs) folder. 

Next, navigate to the folder [Assets/Script]() to find the Postman collection that will be used to create the Search Service elements. 

In Postman, import the collection and fill in the global variables with the proper values. To do that, click on the collection's name and navigate to the "Variables" tab. Modify the values in the "CURRENT VALUE" column according to the following table: 

| CURRENT VALUE | Value to replace |
| ------ | ------ |
| <SEARCH_SERVICE_NAME> | Name of Search Service |
| <SEARCH_SERVICE_ADMIN_KEY> | Admin Key of Search Service |
| <COGNATIVE_SERVICE_KEY> | Key of Cognitive Services |
| <STORAGE_ACCOUNT_NAME> | Name of Storage Account |
| <STORAGE_ACCOUNT_CONTAINER_NAME> | Name of Storage Container |
| <STORAGE_CONTAINER_FOLDER_NAME> | Name of Storage Folder, only if used, otherwise replace with empty space |
| <STORAGE_ACCOUNT_CONNECTION_STRING> | Connection String of Storage Account  |
| <DATASOURCE_NAME> | Name of Datasource |
| <INDEX_NAME> | Name of Index |
| <SKILLSET_NAME> | Name of Skillset |
| <INDEXER_NAME> | Name of Indexer |
| <CUSTOM_SKILL_URL_EXP> | Azure Function URL for Years of Experience skill (after step 4a)|
| <LOOKUP_TABLE_URL_QUAL> | Lookup table URL for Qualifications (after step 4b) |
| <LOOKUP_TABLE_URL_ROLE> | Lookup table URL for Previous roles (after step 4b) |
| <LOOKUP_TABLE_URL_LANG> | Lookup table URL for Languages (after step 4b) |

## Step 2: Create the Datasource
In Postman, navigate to Create Datasource and run the request. 

This will create a Datasource in the Search Service from the container that has the sample CV documents. 

## Step 3: Create the Index
In Postman, navigate to Create Index and run the request. 

This will create an Index in the Search Service for the information to be extracted from the CVs as mentioned earlier.

## Step 4: Create the Skillset 
### Step 4a: Custom Skills
In VS Code, create an HTTP Trigger Azure Function in Python, and replace the code in the "init" file with the code provided in [Assets/Custom Skills](https://github.com/ahmedalm1/cv-knowledge-engine-accelerator-v2/tree/main/Deployment/Assets/Custom%20Skills). This function will be used to calculate the Years of Experience. 

To deploy the function, you can follow the instructions provided in here: [Develop Azure Functions by using Visual Studio Code](https://docs.microsoft.com/en-us/azure/azure-functions/functions-develop-vs-code?tabs=python), and publish the function to a new Function App. 

### Step 4b: Built-in Skills
In Postman, navigate to Create Skillset request. 

For the "Custom Entity Lookup" skills, we need to provide the URL for the CSV lookup tables. You can upload the three tables in [Assets/Lookup Tables](https://github.com/ahmedalm1/cv-knowledge-engine-accelerator-v2/tree/main/Deployment/Assets/Lookup%20Tables) to the Storage Account, and get their SAS URL to be used in the skill definition. After all URLs are provided, run the request.  

This will create a Skillstet in the Search Service that identifies all the information to be extracted from the CVs.

## Step 5: Create the Indexer
In Postman, navigate to Create Indexer and run the request. 

This will create an Indexer in the Search Service that will exctract the defined information from the CVs.

## Step 6: Create the Website Interface
In [Assets/Website Template](https://github.com/ahmedalm1/cv-knowledge-engine-accelerator-v2/tree/main/Deployment/Assets/Website%20Template), open the solution file "CognitiveSearch.Template.sln" in Visual Studio. 

Navigate to the "appsettings.json" file, and change the values according to the following table:

| Placeholder Value | Value to replace |
| ------ | ------ |
| <SEARCH_SERVICE_NAME> | Name of Cognitive Search Service |
| <SEARCH_SERVICE_KEY> | Admin Key of Cognitive Search Service |
| <INDEX_NAME> | Index Name in Search Service |
| <INDEXER_NAME> | Indexer Name in Search Service |
| <STORAGE_ACCOUNT_NAME> | Storage Account Name that stores the documents |
| <STORAGE_ACCOUNT_KEY> | Storage Account Key |
| <CONTAINER_NAME> | Container Name in Storage Account that stores the documents |

You can test the website locally by running the solution in Visual Studio, or publish the website to Azure by following the instructions found here: [Quickstart: Publish an ASP.NET web app](https://docs.microsoft.com/en-US/visualstudio/deployment/quickstart-deploy-aspnet-web-app?view=vs-2019&tabs=azure).

## Step 7: Create the PowerBI Dashboard
TO-DO
