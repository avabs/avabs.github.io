- While you can deploy Linux web apps on Azure App Service, there are a number of limitations. App Service on Linux isn’t supported on the shared pricing tier.  You are not able to mix Windows and Linux apps in the same App Service plan. You can’t mix Windows and Linux apps in the same region within the same resource group.

- Creating App Service Plan firstly gives better idea of how can App Services are brought into same service container, although If you directly create an App Service it will automatically create App Service Plan.

- App Service Plan can have mutliple application running inside it. Depending upon the kind of pricing tier we have.

- The Advanced Tools are what App Service deployments are built on top of. The advanced tools engine is called Kudu. 

- Azure Container Instances is development and deployment oriented. Provides Hypervisor Isolation, which makes sure that you're organization is not sharing the OS Kernel.

- Azure Kubernetes Service, manage and deploy kuberenetes.

- Azure Container Registry. allows to store and manage container image in the central registry.

- Azure Service Fabric, allows to build and operate always, scalable and distributed apps


#### Multi Stage Builds
- Mutiple docker files could be maintained as single Dockerfile where each dockerfile is a stage.


#### Building Container with Azure DevOps

- Docker images can be pushed to a Registry created using ACR

- Containers are deployed in container groups. Container groups are a similar concept to Kubernetes pods. They are a grouping of containers and run on the same hardware and use the same networking.


### Azure AI

#### Azure AI Service
- **Azure Machine Learning Studio** is go to for Machine learning use cases. **Azure Batch AI** is more comprehensive than the Machine learning Studio, provides more access for the ML model's deployment
- **Azure Cognitive Services API** are the ready-made model which can be incorporated in an application for leveraging cognitive services such as speech-to-text. **Azure Bot Service** could be helpful for creating a interactive agents such as chatbots.

### IoT

- Azure Event Hub & IoT Hub
    - Event Hub is a door for the events sent by application interfaces to the event hub endpoint where event hub makes sure the event is proper.
    - IoT hub lets you push data back to the endpoints or application which emitted the event

- Azure Event Grid routes the ingested events to event handlers
- IoT Edge lets you run code on the client side which could be useful for firmware upgrades etc. These are done with the help of Azure IoT edge runtime.

- Azure Service Bus is more generalized Event hub. It is the messaging communication channel between the application and the services.
    - Topic and Subscription works differently from the Queue, One publishes message to a topic which get distriuted to mutliple subscriber 
    of it, wherein Queue provides processing of a single message by reciever.

### Azure Messaging Service
 
 #### Azure Storage Queue
 - Messaging queing system.
 - Main difference between Azure Service Bus and Azure storage queue is the service bus has the order of the messaged queued and the size of message it takes. 
 #### Azure Relay
 - It is a sytem which lets you conect corporate enterprise connection to a public cloud without opening firewall and changing network configuration.


### Azure Media Services

- Handles storage, encoding and packaging the video for the live streaming delivery.
- **Video Indexer**, **Computer Vision** provides analytics over video and images.
- Video Codec is a piece of software which compresses or decompresses media
- **Media Anayltics** for the intelligence.


### Azure Monitor 
- It provides System level monitoring. Application Insights could be used in order to acheive one-to-one monitoring with application.

### Azure Analytics 
- Similar to Splunk and ELK stack.


### Azure Health 
- First line of the defense for identifying the problems with the azure resources.
- Azure Status - provides information on the global issue, not specific to your account.
- Azure Service Health - Just like Azure Status but specific to your account.
- Azure Resource Health - More granular level of the details regarding an Azure Resource.

### Azure Advisor 
- Information and suggestion on Security, Availability, Performance and Cost.

### Azure Activity Log 
- Records events using event data from Azure Resource Manager.


### Azure Network Watcher 
- Monitors what happens between different resources. Analyzing network events.

### Azure Security Center 
- Centralized dashboard for the security of the infrastructure.

### Azure Event Grid
- Automating responses to azure and non-azure events. 

### Automation
- Automation of technologies using Chef and Puppet.
- Runbooks could be used for automation, these are collection of the powershell scripts.

### Azure Managed Application
- Azure Managed Application are the cloud solutions that could be deployed and operated by the customers. Managed Application are published to Azure Marke
et place so that it is available to all customers. These resources are deployed to Resource Group of the Consumer, where even the publisher of Managed 
Application has access to.



