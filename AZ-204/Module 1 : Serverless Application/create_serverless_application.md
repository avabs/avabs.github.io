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

#### Important Points
- WebJobs are the only technology that permits developers to control retry policies.
- Azure Logic Apps is the only one of the four technologies that provides a design-first approach intended for developers.


### Creating a serveless application

#### Function App 
- A function hold in execution environment called function app
- A Function App may use these types of plan
  - Consumption Plan
    - True Serverless since provides automatic scalling and bills only for running of the function and configurable timeout.
  - Azure App Service Plan 
    - Function runs continuously on the VM and user's responsible for the application resource and ideal for continuosly running applications/functions
- Storage account is required, gets used in loogin function executions and managing executions triggers, in the case of **Consumption Plan**, code and configuration file is stored in it.
- Triggers
  - Functions are event driven, which means they run in response to an event. The type of event that starts a function is called a trigger. Each function must be configured with exactly one trigger.
- Bindings
 - A binding is a declarative way to connect data and services to your function. Bindings interact with various data sources, which means you don't have to write the code in your function to connect to data sources and manage connections--the platform takes care of that complexity for you as part of the binding code. Each binding has a direction--your code reads data from input bindings, and writes data to output bindings. Each function can have zero or more bindings to manage sthe input and output data processed by the function.
 - Trigger is type of an input binding
 
