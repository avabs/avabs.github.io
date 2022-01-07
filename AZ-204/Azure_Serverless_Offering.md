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
- A Function App is a container that specifies the operating system and resources, such as the memory, computing power, and disk space, for running an Azure function. Behind the scenes, an Azure Function App is a collection of one or more virtual machines (VMs) running a web server.
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
 - Timer trigger
  - ![image](https://user-images.githubusercontent.com/36666451/144472301-a888bd70-f994-427e-b151-73f245d6555d.png)

- **Azure Storage** is Microsoft's cloud storage solution that supports all types of data, including: blobs, queues, and NoSQL.

- **Azure Blob Storage** is a solution to store unstructured data which can be appended as well. Useful for log files which is being constantly appended. Blob Storage is great at storing text or binary files.

- In an **Azure Cosmos DB**, a container is used to store a variety of user-generated entities, also called items.

#### Durable functions 
- Unlike Functions, Durable functions operates in stateful environment.
  - Event driven code e.g. can wait asynchronously for events and perform task in response
  - Can be chained together and be ordered
  - Has orchestration function, which manages workflws (directly coded)
    - Functions could be both sync and async
    - state preserve and resource saving is done when function seats idle/waits

- Functions Types 
  - Client functions are the entry point for creating an instance of a Durable Functions orchestration. They can run in response to an event from many sources, such as a new HTTP request arriving, a message being posted to a message queue, an event arriving in an event stream. You can write them in any of the supported languages.

  - Orchestrator functions describe how actions are executed, and the order in which they are run. You write the orchestration logic in code (C# or JavaScript).

  - Activity functions are the basic units of work in a durable function orchestration. An activity function contains the actual work performed by the tasks being orchestrated.

  - Orchestrator will call the activity functions.
##### Authorization on the Azure Functions
- Anonymous 
  - Anyone can request the API endpoint
- Function
  - Function key required to authorize the request sent to Azure Functions. Function specific.
- Admin
  - Same as function but has overall access.

#### Azure Functions Core Tools
- Let's you develop and run function on your local environment


#### Secret in Github Webhook
-When your secret token is set, GitHub uses it to create a hash signature for each payload. This hash signature is passed along with each request in the headers as x-hub-signature.

When your function receives a request, you need to compute the hash using your secret, and ensure that it matches the hash in the request header. GitHub uses an HMAC SHA1 hex digest to compute the hash, so you must calculate your hash in this same way, using the key of your secret and your payload body. The hash signature starts with the text sha1=.


##### Change feed
- Azure Cosmos DB exposes a "change feed". The change feed support in Azure Cosmos DB works by listening to a database container for changes.


#### SignalR
- SignalR is an abstraction for a series of technologies that allows your app to enjoy two-way communication between the client and server. SignalR handles connection management automatically, and lets you broadcast messages to all connected clients simultaneously, like a chat room. You can also send messages to specific clients. The connection between the client and server is persistent, unlike a classic HTTP connection, which is re-established for each communication.

- SignalR could use Websockets API by default for HTML5 application, Server Sent Events(Event Source) and Ajax in this order.

- When you copy files to a storage container named $web, those files are available to web browsers via a secure server

#### Azure API Management

- Cloud Service that is used to publish, secure, transform and maintain the API.
- Comping mutliple application exposing APIs and functions into a single entry point.
- We can use API management to forward the requests.

#### Custom Handlers
- a custom handler is a web server. The web server receives events from the Functions host. You then have an opportunity to write code in your preferred language to respond to the events.
- A message queue is a software component that's used to handle messaging between processes, threads, or applications. A queue can store a message, and workers can fetch the message when it's a good time.
