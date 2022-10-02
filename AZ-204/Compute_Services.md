
## Azure Availability Sets
- Azure consists of racks upon racks of the server and, each rack could be a **Fault Domain**. 
- Availability Sets distributes workload mutliple Fault Domains. 
- Grouping VMs in an availability sets also gives the Windows Azure Fabric Controller (FC) the information it needs to intelligently update the host OSs that your guest VMs are running on. Without availability sets the FC would have no idea that two machines were serving the same purpose and could reasonable take them both down for host OS updates.
- An Availability Set also makes use of Update Domains. This allow you to determine how many of the workloads are down at any given time. 
- You can set a priority order for shutting down the VMs and the number of update domains determines how many machines will be involved in the shutdown. 
- Reference - https://www.softnas.com/docs/softnas/v3/html/azure_availability_sets.html


## Azure App Service
- While you can deploy Linux web apps on Azure App Service, there are a number of limitations. 
- App Service on Linux isn’t supported on the shared pricing tier.
- You are not able to mix Windows and Linux apps in the same App Service plan. 
- You can’t mix Windows and Linux apps in the same region within the same resource group.

- Creating App Service Plan firstly gives better idea of how can App Services are brought into same service container, although If you 
directly create an App Service it will automatically create App Service Plan.

- App Service Plan can have mutliple application running inside it. Depending upon the kind of pricing tier we have.

- In App service plan, we get Isolated environment where we get the dedicated computing environment

- The Advanced Tools are what App Service deployments are built on top of. The advanced tools engine is called Kudu. 

- By default azure domain names such as azurewebsites are secured and can be accessed over http and https protocols, but having a
custom domain and securing that requires SSL and TLS certification.

## Azure Container Service & Azure Kubernetes Service
- Azure Container Instances is development and deployment oriented. Provides Hypervisor Isolation, which makes sure that you're organization is not sharing the OS Kernel.

- Azure Kubernetes Service, manage and deploy kuberenetes.

- Azure Container Registry. allows to store and manage container image in the central registry.

## Azure Service Fabric
- Azure Service Fabric, allows to build and operate always, scalable and distributed apps


## Building Container with Azure DevOps
- Docker images can be pushed to a Registry created using ACR
- Containers are deployed in container groups. Container groups are a similar concept to Kubernetes pods. They are a grouping of containers and run on the same hardware and use the same networking.
- Mutiple docker files could be maintained as single Dockerfile where each dockerfile is a stage.



## Azure Serverless Services
- Serverless tasks are billed upon execution of the business logic.
- Here, Serverless must be interpreted as Cloud Tenant put efforts and time in developing the application rather than managing the infrastructure so it is done automatically i.e. scales up/down automatically
- Business process modeled in software are often called as workflows.
- Workflows can be implemented using following azure services since all of them take input, have action
on them, conditions and produces output
  - Logic Apps
  - Microsoft Power Automate
  - WebJobs
  - Azure Functions
    
### Design-first technologies
- Approches to Designing the workflow firstly 
    - #### Logic Apps 
        - Logic Apps is visualize and code interface to automate, orchestrate, and integrate disparate components of the distributed application and has power to integrate to external source with the help of connectors i.e. Twitter as connecter may let you read tweets and send as well.
        - A custom connector can be created as well.

    - #### Power Automate
        - Used by busines user rather than developer
    
### Code-first technologies 
- Developers may be inclined towards code first technology since it gives you more refined and custom control over the functions.
- WebJobs are the only technology that permits developers to control retry policies.
- Azure Logic Apps is the only one of the four technologies that provides a design-first approach intended for developers.
    - #### WebJobs and WebJobs SDK
        - Auzre App Service is cloud based hosting service for mobile apps, backends and other services but there are some miscellanous task that runs as background process for a particular action e.g. Compressing the image when an image is uploaded.
        - WebJobs can help with these task in 2 manner
        - Continuous - Keeps running the job 
        - Triggered - Must be triggered or scheduled
        - WebJobs has few limitations, it only supports ASP.NET / SDK 2.x; however SDK 3.x supports .NET Core.
        - WebJobsSDK can only be used with .NET languages.

    - #### Azure Functions 
        - Another way to write code for triggered based events
        - Supports many languages than WebJobs / WebJobs SDK
        - You pay for time your code runs
        - Code can be hosted on SCM 
        - Integrate within Azure and Third parties
        - Azure Function could be hosted in 3 pricing tiers 
        - Consumption 
            - Default hosting plan
            - Automatic scalling 
        - Premium 
            - Provides more control over the compute resource that could be used
            - Max execution time
            - Provides virtual network connectivity
            - Support to run function on the custom linux image. 
        - Dedicated (App Service) plan 
            - Runs functions withing your app service plan 
        - Types 
            - HTTPTrigger - on http event
            - TimerTrigger - Scheduled trigger
            - BlobTrigger - When blob gets added to storage account
            - CosmosDBTrigger - code excutes in response to updates in CosmosDB
        - Runtimes provided by the Azure Functions are Docker containers.
        - Azure Function hosting - Windows vs Linux. Windows provide better experience in terms of features than Linux.
        - #### Creating a serveless application
            - #### Function App 
                - A function hold in execution environment called function app
                - A Function App is a container that specifies the operating system and resources, such as the memory, computing power, and disk space, for running an Azure function. Behind the scenes, an Azure Function App is a collection of one or more virtual machines (VMs) running a web server.
                - A Function App may use these types of plan
                - Consumption Plan
                    - True Serverless since provides automatic scalling and bills only for running of the function and configurable timeout.
                - Azure App Service Plan 
                    - Function runs continuously on the VM and user's responsible for the application resource and ideal for continuosly running applications/functions
                - Storage account is required, gets used in loogin function executions and managing executions triggers, in the case of **Consumption Plan**, code and configuration file is stored in it.
                - Triggers
                - Functions are event driven, which means they run in response to an event. The type of event that starts a function is called a trigger. **Each function must be configured with exactly one trigger**.
                - Bindings
                - A binding is a declarative way to connect data and services to your function. Bindings interact with various data sources, which means you don't have to write the code in your function to connect to data sources and manage connections--the platform takes care of that complexity for you as part of the binding code. Each binding has a direction--your code reads data from input bindings, and writes data to output bindings. Each function can have zero or more bindings to manage sthe input and output data processed by the function.
                - Input bindings are the data sources that will be passed to function when it gets triggered.
                - Trigger is type of an input binding
                - Timer trigger
                - ![image](https://user-images.githubusercontent.com/36666451/144472301-a888bd70-f994-427e-b151-73f245d6555d.png)
                - Azure Functions requires Storage Account
                - **Azure Storage** is Microsoft's cloud storage solution that supports all types of data, including: blobs, queues, and NoSQL.

                - **Azure Blob Storage** is a solution to store unstructured data which can be appended as well. Useful for log files which is being constantly appended. Blob Storage is great at storing text or binary files.

                - **Azure Files** also can be used by Azure Functions

                - In an **Azure Cosmos DB**, a container is used to store a variety of user-generated entities, also called items.

            - #### Durable functions 
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
                - Orchestrator must always call deteministic APIs which returns same output for same input, no matter how often they are called.
            - ##### Authorization on the Azure Functions
                - Anonymous 
                    - Anyone can request the API endpoint
                - Function
                    - Function key required to authorize the request sent to Azure Functions. Function specific.
                - Admin
                    - Same as function but has overall access.

            - #### Azure Functions Core Tools
                - Let's you develop and run function on your local environment

