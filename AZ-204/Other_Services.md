### Azure AI

#### Azure AI Service
- **Azure Machine Learning Studio** is go to for Machine learning use cases. **Azure Batch AI** is more comprehensive than the Machine learning Studio, provides more access for the ML model's deployment
- **Azure Cognitive Services API** are the ready-made model which can be incorporated in an application for leveraging cognitive services such as speech-to-text. **Azure Bot Service** could be helpful for creating a interactive agents such as chatbots.

### IoT
- Azure Event Hub & IoT Hub
    - Event Hub is a door for the events sent by application interfaces to the event hub endpoint where event hub makes sure the event is proper.
    - Basic Tier of the Event Hub does not support Kafka Messages.
    - A centralized service to collect data and logs from other Azure services.
    - IoT hub lets you push data back to the endpoints or application which emitted the event

- Azure Event Grid routes the ingested events to event handlers
- IoT Edge lets you run code on the client side which could be useful for firmware upgrades etc. These are done with the help of Azure IoT edge runtime.

- Azure Service Bus is more generalized Event hub. It is the messaging communication channel between the application and the services.
    - Topic and Subscription works differently from the Queue, One publishes message to a topic which get distriuted to mutliple subscriber 
    of it, wherein Queue provides processing of a single message by reciever.
    - Example : A mobile application which consists of the multiple backends systems such as Accounting, HR. We can create topics for these backend application so that whenever an event occurs, messages could be published to such topic and another mobile backend can subscribe to these topics and pass on the information **Notification hub** to user's as push notification.

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

### Autoscale
- Vertical
	- Changing the capacity of the current resource
- Horizontal 
	- Adding more of the same resource type or application
- Autoscaling for virtual machines in Azure is supported through **Azure VM Scale Sets (VMSS)**, which are identically configured. A VM scale set service is used to design sets of identical and load-balanced Virtual Machines (VMs).
- Azure monitor provides support for autoscale and Azure diagnostics could be used to implement custom logic for autoscaling.

### Azure Redis Cache
- Temporarly copying frequently accessed data into fast storage (memory) which is close to Application.
- Azure Redis Cache is accessible to Application withing Azure and outside to it.

### Azure Content Delivery Network (CDN)
- Putting content in the edge servers which could be fetched by user with lesser latency.
- When requesting to origin server, origin server will forward the request of the user to point of the presence location which are closer to user.	

### Azure API Management
- Cloud Service that is used to publish, secure, transform and maintain the API.
- Comping mutliple application exposing APIs and functions into a single entry point.
- We can use API management to forward the requests.

### Custom Handlers
- a custom handler is a web server. The web server receives events from the Functions host. You then have an opportunity to write code in your preferred language to respond to the events.
- A message queue is a software component that's used to handle messaging between processes, threads, or applications. A queue can store a message, and workers can fetch the message when it's a good time.


#### Other Services
- Azure Log Analytics is where all the logs are stored for the analysis
- Azure Automation is the service which lets you automate few mundane tasks such as the update management, patching of the VMs.
