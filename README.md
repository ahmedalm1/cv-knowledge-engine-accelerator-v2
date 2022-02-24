# CV Knowledge Engine Solution Accelerator V2

## About this accelerator
The CV Knowledge Engine solution accelerator aims to provides a quick way of creating an intelligent search engine, that enables searching and filtering through CV and resume documents. It leverages Knowledge Mining and Azure Cognitive Services technologies, to extract the valuable information and insights from CV documents, like names, contact information, years of experience, skills and qualifications, ..etc. It also creates an intuitive, easy-to-navigate user interface, that allows for a full search experience with capabilities like searching with search terms, customized filters, and comprehensive result cards. Moreover, the extracted information can also be exported to Power BI and used to create informative dashboards, to give a high level overview of the extracted information. 

> #### Note
> 
> This is an updated version of the CV Knowledge Engine Solution Accelerator.
> You can find the older version here ([CV Knowledge Engine Solution Accelerator](https://github.com/ahmedalm1/cv-knowledge-engine-accelerator))

## Business Use Case 
The process of screening and searching through CV documents submitted by job seekers is a long and a costly one, where the recruiting teams usually have to go through each submitted CV manually, to find the best candidates suited for the job opening. This accelerator will help extract the essential information from CVs and resumes, and simplify the process of searching and filtering through applicants, which will significantly reduce costs and time-to-insights. 

## Architecture and Resources
The following are the Azure resources that are required to deploy this accelerator, along with the architecture of the solution: 
- Storage Account -- to store the submitted CV documents 
- Cognitive Search -- to index the extracted infromation from CVs
- Cognitive Services -- to extract the desired candidates information 
- Function App -- to host the custom skills used by the indexer
- App Service -- to host the search engine website 

![Architecture](https://user-images.githubusercontent.com/88718044/147383469-bce1ecb2-1e90-4bf2-b780-e49ad62aa186.png)

## Extracted Information
The information and insights extracted from the CV documents can be grouped into three categories: 

### PII Information
- Name 
- Email
- Phone number
- Location 
- Links (LinkedIn, portfolio website, ..etc.) 
### Professional Information
- Years of experience
- Qualifications
- Previous roles
- Skills
- Languages 
### Other Insights
- Key phrases

## User Interface 
The extracted CV information is stored in a search index, that can then be used to create two ways of displaying and querying the information. The first is a search engine interface hosted in a web app on Azure, and the second is a Power BI report with a high-level dashboard to view the information. 

### Search Engine Interface
Using the provided web app template, a search engine interface can be created to search and filter through the extracted information from the CVs. This interface allows for a complete search engine experience including full-text search, custom filters, and comperhensive result cards. 

#### Home Page
![Home Page](https://user-images.githubusercontent.com/88718044/147383789-6b88bf5f-69e9-4bc9-bc08-3121af43cabc.png)

#### Search Results
![Search Results](https://user-images.githubusercontent.com/88718044/155551827-9d079345-3f58-4d8a-a6de-3e9e67f75533.png)

### Power BI Report
Using the provided Power BI report template, a high-level dashboard can be created to display the information extracted from CVs. 

#### Dashboard
![Dashboard](https://user-images.githubusercontent.com/88718044/155554049-872bd577-910d-444b-8580-b3a8905f2f39.png)

## References 
This accelerator was built as a continuation of the Knowledge Mining Solution Accelerator. 
You can find the original project here ([Knowledge Mining Solution Accelerator](https://github.com/Azure-Samples/azure-search-knowledge-mining))

## License
For all licensing information refer to [LICENSE](https://github.com/ahmedalm1/cv-knowledge-engine-accelerator-v2/blob/main/LICENSE).
