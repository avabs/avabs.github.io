### Serverless Application

- Here, Serverless must be interpreted as Cloud Tenant put efforts and time in developing the application rather than managing the infrastructure so it is done automatically i.e. scales up/down automatically
- Business process modeled in software are often called as workflows.
- Workflows can be implemented using following azure services since all of them take input, have action
on them, conditions and produces output
  - Logic Apps
  - Microsoft Power Automate
  - WebJobs
  - Azure Functions
    
#### Design-first technologies
- Approches to Designing the workflow firstly 

##### Logic Apps 
- Logic Apps is visualize and code interface to automate, orchestrate, and integrate disparate components of the distributed application and has power to integrate to external source with the help of connectors i.e. Twitter as connecter may let you read tweets and send as well.
- A custom connector can be created as well.

#### Power Automate
- Used by busines user rather than developer
#### Code-first technologies 
- Developers may be inclined towards code first technology since it gives you more refined and custom control over the functions.

#### WebJobs and WebJobs SDK
- Auzre App Service is cloud based hosting service for mobile apps, backends and other services but there are some miscellanous task that runs as background process for a particular action e.g. Compressing the image when an image is uploaded.
- WebJobs can help with these task in 2 manner
  - Continuous - Keeps running the job 
  - Triggered - Must be triggered or scheduled
  - WebJobs has few limitations, it only supports ASP.NET / SDK 2.x; however SDK 3.x supports .NET Core.
- WebJobsSDK can only be used with .NET languages.

#### Azure Functions 
- Another way to write code for triggered based events
- Supports many languages than WebJobs / WebJobs SDK
- You pay for time your code runs
- Code can be hosted on SCM 
- Integrate within Azure and Third parties
- Types 
  - HTTPTrigger - on http event
  - TimerTrigger - Scheduled trigger
  - BlobTrigger - When blob gets added to storage account
  - CosmosDBTrigger - code excutes in response to updates in CosmosDB
