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

## Sample Documents 
The sample documents used to demo this accelerator are 223 open-source dummy CV documents, acquired from [Resume Krafts](https://resumekraft.com/resume-examples/) website.

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

## Deployment 
To deploy this solution accelerator, navigate to the [Deployment](https://github.com/ahmedalm1/cv-knowledge-engine-accelerator-v2/tree/main/Deployment) page and follow the simple steps. 

## References 
This accelerator was built as a continuation of the Knowledge Mining Solution Accelerator. 
You can find the original project here ([Knowledge Mining Solution Accelerator](https://github.com/Azure-Samples/azure-search-knowledge-mining))

## License
For all licensing information refer to [LICENSE](https://github.com/ahmedalm1/cv-knowledge-engine-accelerator-v2/blob/main/LICENSE).

## General Guidelines

When you're getting ready to deploy AI-powered products or features, the following activities help to set you up for success:

- Understand what it can do: Fully assess the capabilities of any AI model you are using to understand its capabilities and limitations. Understand how it will perform in your particular scenario and context.

- Respect an individual's right to privacy: Only collect data and information from individuals for lawful and justifiable purposes. Only use data and information that you have consent to use for this purpose.

- Legal review: Obtain appropriate legal advice to review your solution, particularly if you will use it in sensitive or high-risk applications. Understand what restrictions you might need to work within and your responsibility to resolve any issues that might come up in the future. 

- System review: If you're planning to integrate and responsibly use an AI-powered product or feature into an existing system of software, customers or organizational processes, take the time to understand how each part of your system will be affected.

- Human in the loop: Keep a human in the loop, and include human oversight as a consistent pattern area to explore. This means constant human oversight of the AI-powered product or feature and maintaining the role of humans in decision-making. Ensure you can have real-time human intervention in the solution to prevent harm. This enables you to manage where the AI model doesn't perform as required.

- Security: Ensure your solution is secure and has adequate controls to preserve the integrity of your content and prevent unauthorized access.

## Notes

- Responsible use cases for the accelerator : The accelerator is meant to quicken the applicant screening process for recruiters by providing a way to filter the CVs by their professional attributes, such as skills, years of experience, previous roles, etc. However, the accelerator should not be used to filter candidates based on candidates' PII information such as age, gender, name, email, etc.

- A person should always be involved to review the data sources and output

- The search index does not and should not be used to rank or prioritize CV results. The candidates should only be filtered on their professional attributes, the personal attributes like age, gender, name, email, phone, etc. do not and should not influence the search results

- The accelerator only supports English language CVs, in Word or PDF format. Other language CVs and document format types have not been tested as part of this accelerator.

- Data from candidates used should be obtained only by consent and following all applicable laws

