# CV Knowledge Engine Solution Accelerator V2

## About this accelerator
The CV Knowledge Engine solution accelerator aims to provides a quick way of creating an intelligent search engine, that enables searching and filtering through CV and resume documents. It leverages Knowledge Mining and Azure Cognitive Services technologies, to extract the valuable information and insights from CV documents, like names, contact information, years of experience, skills and qualifications, ..etc. It also creates an intuitive, easy-to-navigate user interface, that allows for a full search experience with capabilities like searching with search terms, customized filters, and comprehensive result cards. Moreover, the extracted information can also be exported to Power BI and used to create informative dashboards, to give a high level overview of the extracted information. 

> #### Note
> 
> This is an updated version of the CV Knowledge Engine Solution Accelerator.
> You can find the older version here ([CV Knowledge Engine Solution Accelerator V1](https://github.com/AhmedAlmu/cv-knowledge-engine-accelerator))

## Business Use Case 
The process of screening and searching through CV documents submitted by job seekers is a long and a costly one, where the recruiting teams usually have to go through each submitted CV manually, to find the best candidates suited for the job opening. This accelerator will help extract the essential information from CVs and resumes, and simplify the process of searching and filtering through applicants, which will significantly reduce costs and time-to-insights. 

## Architecture and Resources
The following are the Azure resources that are required to deploy this accelerator, along with the architecture of the solution: 
- Storage Account -- to store the submitted CV documents 
- Cognitive Search -- to index the extracted infromation from CVs
- Cognitive Services -- to extract the desired candidates information 
- Function App -- to host the custom skills used by the indexer
- App Service -- to host the search engine website 

![Architecture](![image](https://user-images.githubusercontent.com/88718044/147383469-bce1ecb2-1e90-4bf2-b780-e49ad62aa186.png))

