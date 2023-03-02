## Azure Virtual Machines
- Lets you choose your OS, memory, and storage.
- Comes at the cost of maintaining the software level services such OS patches.    
- These are billed at hourly rate.
- SLA of 99.9% (When all the storage options are premium)
- Components when VM gets created
    - **Network Security Group**
        - Attached to Network Interface Component, Virtual firewall with rules around ports and protocols.
    - **Network Interface Component** 
        - A device that handles the ip and network communication 
    - **Virtual machine** itself
    - **Public IP Address**
    - **Virtual Network** - Network where your VM will reside
- You can bring your linux by creating a **Linux Virtual Hard Disk (VHD)**

- **Cloud-Init**
    - Cloud-init is the industry standard multi-distribution method for cross-platform cloud instance initialization. It is supported across all major public cloud providers, provisioning systems for private cloud infrastructure, and bare metal installations.
    - Cloud instance initialization is the process of the preparing the instance with all the configuration data for the operating system and runtime environment.
        - Cloud instances are intialized from a disk image and instance data
            - **Meta-data**
            - **User-data** - it is the script that you want to run when an instance first boots up. Eg. Install Apache web-server
            - **Vendor-data**
    - ARM (infrastructure as code) is **cloud init** underneath
    - Cloud init only works for linux distribution.

- Azure VMs are categorized into 
    - Types
        - General Purpose
        - Compute Optimized  
        - Memory Optimized
        - Storage Optimized
        - GPU
        - High Performance Compute
    - Size
        - Also called series and SKU 
        - Multiple options are there        
        - B, D*
        - F* 
        - E*, M 
        - L*
        - N*
        - H*
- **Azure Compute Unit (ACU)**
    - Provides a way of comparing compute performance across Azure SKUs. It is standardized on a Small (Standard_A1) with a value of 100.
- **Hyper-V** is the Microsoft's hardware virtualization product. How we have **Virtual Box** for linux and MacOS.
- Azure Gen 1 and Gen 2
    - Gen 1 are the BIOS boot based arch
    - Gen 2 are Uefi boot based arch, secure boot and can have larger boot volume upto 64 TB.
- **SSH, RDP and Bastions**
    - SSH (Secure Shell) is protocol to establish a secure connection  between a client and server, happens on port 22.
        - SSH Key pairs is when you generate out two keys 
            - Private and public keys
            - Private Key remains on the local system and public key is stored on VM.
            - When you SSH, you provide your private key which is matched against public.
    - RDP (Remote Desktop Protocol) is proprietary protocol developed Microsoft which provides a user with GUI to connect to another computer over a
        network connection, happens on port 3389 using TCP and UDP, you can only connect to windows server via Visual Desktop 
        - This only works with Windows Server.
    - Bastions, it is an azure service, which gets deployed and lets you connect over browser to the VM. It has its own subnet. It would get use where you don't have SSH client or RDP client such as chromebook.

- **Windows vs Linux Server**
    - Windows server requires a license
    - Requires user name and password
    - Much larger instancee to run Windows at least a B2
    - Linux requires no licenses

- **Update Management**
    - Allows to manage and install OS patches and updates for both windows and linux that are deployed in Azure, on-premises, or in other cloud providers.
      
## Azure Availability Sets
- Azure consists of racks upon racks of the server and, each rack could be a **Fault Domain**. 
- Availability Sets distributes workload mutliple Fault Domains. 
- Grouping VMs in an availability sets also gives the Windows Azure Fabric Controller (FC) the information it needs to intelligently update the host OSs that your guest VMs are running on. Without availability sets the FC would have no idea that two machines were serving the same purpose and could reasonable take them both down for host OS updates.
- An Availability Set also makes use of Update Domains. This allow you to determine how many of the workloads are down at any given time. 
- You can set a priority order for shutting down the VMs and the number of update domains determines how many machines will be involved in the shutdown. 
- Reference - https://www.softnas.com/docs/softnas/v3/html/azure_availability_sets.html


## Azure App Service
- Azure App Service is HTTP based service for hosting web applications, REST APIs, and Mobile back ends.
- It is PaaS, so it's the **Heroku** equivalent for Azure or **AWS Elastic Beanstalk**
- Creating App Service Plan firstly gives better idea of how can App Services are brought into same service container, although If you directly create an App Service it will automatically create App Service Plan.
- It takes care of the following underlying infrastructure
    - Security patches for OS and languages
    - Load Balancing
    - Autoscaling
    - Automated manager
- App service makes it easy to implement common integration and features such as 
    - Azure DevOps (For Deployments)
    - Github Integration
    - Docker Hub Integration
    - Package Management
    - Custom domains
    - Attaching TLS/SSL certificates
- Pricing Tiers
    - Shared Tier - Free and Shared - Linux based instances are not supported
    - Dedicated Tier - Basic, Standard, Premium, PremiumV2 and, PremiumV3
    - Isolated Tier
- Azure App service can also run docker single or multi-containers
- While you can deploy Linux web apps on Azure App Service, there are a number of limitations. 
- App Service on Linux isn’t supported on the shared pricing tier.
- You are not able to mix Windows and Linux apps in the same App Service plan. 
- You can’t mix Windows and Linux apps in the same region within the same resource group.
- App Service Plan can have mutliple application running inside it. Depending upon the kind of pricing tier we have.
- The Advanced Tools are what App Service deployments are built on top of. The advanced tools engine is called Kudu. 
- By default azure domain names such as azurewebsites are secured and can be accessed over http and https protocols, but having a custom domain and securing that requires SSL and TLS certification.
- App service plan needs to be in standard/premium for Backup/Restore option.

### Runtime Environment
- A runtime for Azure App Service will be a pre-defined container that your programming language and commonly used libs for that language installed.

Solution for language that are not supported 
- Create a custom docker container
- Deploy it to ACR 
- Deploy image to App Service 

### Deployment Slots
- Create different enviroments of your web application associated to a different hostname. This is useful when need a staging or QA environment
- You can swap environment, this is how you can perform a Blue/Green deployment

### App Service Environment
- Provides a fully isolated and dedicated environment for securely running App Service apps at high scale
- This allows 
    - Windows Web app
    - Linux Web App
    - Docker containers
    - Mobile apps
    - Function
- Ideal for workloads that require
    - Very high scale 
    - Isolation and secure network access
    - High memory utilization
- ASEs can be deployed in single or across mutliple regions. Ideal for horizontal scaling stateless application tiers in support of high requests per second (RPS) workloads
- ASE only supported in Isolated tier
- WAF can be applied here.
- ASEs can be deployed to availability zones using zone pinning.

- Deployment types for an ASE
    - External ASE
        - Exposes the ASE hosted app on an internet-accessible IP address.
    - ILB ASE
        - Addition of Internal Load Balancer is the only difference here.

### Deployment
The action of pushing changes or updates from a local environment or repository into a remote environment. 
Azure App Services provides many ways to deploy your applications: 
- Run from Package 
    - Since other deployement get mounted at /home/site/wwwroot, but in case of package the zip itself becomes the readonly wwwroot so it escapes the filelock conflicts
- Deploy ZIP or WAR (Uses Kudu) 
    - Kudu engine provides CI based deployments, it is the engine behind git deployments
- Deploy via FTP 
    - Needs FTP client and just drag and drop
- Deploy via cloud sync (Dropbox or One Drive) 
- Deploy continuously (GitHub, BitBucket, and Azure Repos) uses Kudu and Azure Pipelines 
- Deploy using a custom container Cl/CD pipeline (Deploy for Docker Hub or Azure Container Registry) 
- Deploy from local Git (Kudu build server,) 
- Deploy using Github Actions 
- Deploy using Github Actions containers 
- Deploy with template (ARM templates

### WebJobs
- Program or script runs in the same instance as a web app, API app, or mobile app.
- Not supported by App Service on Linux
- Types
    - Continuous
        - runs continuosly until stopped
    - Triggered
        - run only when triggered

## Azure Container Service & Azure Kubernetes Service
- Azure Container Instances is development and deployment oriented. Provides Hypervisor Isolation, which makes sure that you're organization is not sharing the OS Kernel.
- Azure Kubernetes Service, manage and deploy kuberenetes.
- Azure Container Registry. allows to store and manage container image in the central registry.

## Azure Container Instances 
- Package, deploy and manage cloud applications using containers. Fully managed docker as service.
- You only deal with containers here without having to worry about the virtual machine setup.
- Ideally for 
    - Simple application
    - Task Automation
    - Build Jobs
- Can be provisioned within seconds
- Have custom sizing of the vCPUs, Memory and GPUs where VMs sizes are determined.
- Can deploy both windows and linux containers
- Can persist storage with Azure Files
    - Secret Volume, Empty Directory and Cloud Git Repo
- ACIs are accessed via a fully qualified domain name
- Can pull images from 
    - ACR
    - dockerhub
    - private registries
- Container Groups are container groups which gets scheduled on the same host machine, these share 
    - lifecycle
    - resources
    - network 
    - storage volumes
- Container Groups are similar to Kubernetes Pods
- Multi container groups currently supports only Linux containers
- ![multi](https://user-images.githubusercontent.com/36666451/196981849-c8bf80c5-94b7-469b-b746-755bd25084d8.png)
- Ways to creats multi container groups 
    - ARM
    - YAML
- Restart Policy 
    - Always, Never and OnFailure
- Commands are 
    - az container logs, az container exec 


## Azure Container Registry
- A private registry to maintain and create your docker images.
- Managed private docker registry based upon **open-source docker registry 2.0**
- Azure registry tasks to build container images in Azure
- ACR tasks allow you to automate OS and framework patching for your docker containers.
- Deployment targets where images could be pulled
    - kuberntes
    - DC/OS
    - docker swarm

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
        - Consumption (Cold Starts)
            - Default hosting plan
            - Automatic scalling 
        - Premium (Pre warmed)
            - Provides more control over the compute resource that could be used
            - Max execution time
            - Provides virtual network connectivity
            - Support to run function on the custom linux image. 
        - Dedicated (App Service) plan (VM Sharing)
            - Runs functions withing your app service plan, so no extra cost for runnign the azure functions
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
                - Trigger is type of an input binding.
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
                - Has orchestration function, which manages workflows (directly coded)
                    - Functions could be both sync and async
                    - State preserve and resource saving is done when function seats idle/waits

                - Functions Types 
                    - **Client functions** are the entry point for creating an instance of a Durable Functions orchestration. They can run in response to an event from many sources, such as a new HTTP request arriving, a message being posted to a message queue, an event arriving in an event stream. You can write them in any of the supported languages.

                    - **Orchestrator functions** describe how actions are executed, and the order in which they are run. You write the orchestration logic in code (C# or JavaScript).

                    - Activity functions are the basic units of work in a durable function orchestration. An activity function contains the actual work performed by the tasks being orchestrated.

                    - Orchestrator will call the activity functions.
                    
                    - Orchestrator must always call deteministic APIs which returns same output for same input, no matter how often they are called.
                    
                    - Output from the called function can be saved to a variable, which will still hold data even if process recycles or VM reboots. 
                    This is what I understand from a function being stateful in nature. Hence local state is never lost. 
                
                - Patterns of Durable functions
                    - Function chaining
                        - Output of the a function is input to the another function
                    Fan-out/fan-in
                        - Executing multiple function in parallel and waiting for all of them to finish

            - ##### Authorization on the Azure Functions
                - Anonymous 
                    - Anyone can request the API endpoint
                - Function
                    - Function key required to authorize the request sent to Azure Functions. Function specific.
                - Admin
                    - Same as function but has overall access.

            - #### Azure Functions Core Tools
                - Let's you develop and run function on your local environment

            - **function.json** contains bindings, triggers and other configurational information.
            - **hosts.json** contains global configurations options for all the functions within function app.
            - **Custom Handlers** are light weight webserver. These based upon languages which supports HTTP primitives. In simpler words, languages which are not part of azure. This is an executable. It is required to maintain a folder structure with follwoing files
              - hosts.json
              - local.settings.json
              - an executable - handler.exe
              - it should server http request
              - function.json

### Azure Managed Disk Encryption 
- Azure Disk Encryption
	- ADE encrypts the OS and data disks of the VM using **DM-Crypt** in **Linux** or **Bit-Locker** in Windows. ADE can use Azure Key Vault Integration to store the encryption keys and secrets.
- Azure Disk Storage Server-Side Encryption (Encryption at rest) 
	- Auutomatically encrypts the Azure Managed Disk  (OS and the data disk) when persisting them to Storage Clusters.
- Encrption at Host 
	- Ensures that data stored on the VM host hosting your VM is encrypted at rest and flows encrypted to the Storage clusters.
