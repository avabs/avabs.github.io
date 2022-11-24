### Azure AI Service
- **Azure Machine Learning Studio** is go to for Machine learning use cases. **Azure Batch AI** is more comprehensive than the Machine learning Studio, provides more access for the ML model's deployment
- **Azure Cognitive Services API** are the ready-made model which can be incorporated in an application for leveraging cognitive services such as speech-to-text. **Azure Bot Service** could be helpful for creating a interactive agents such as chatbots.

### IoT
- **Azure Event Hub & IoT Hub**
    - **Event Hub** is a door for the events sent by application interfaces to the event hub endpoint where event hub makes sure the event is proper.
    - Basic Tier of the Event Hub does not support Kafka Messages.
    - A centralized service to collect data and logs from other Azure services.
    - **IoT hub** lets you push data back to the endpoints or application which emitted the event

- **Azure Event Grid** routes the ingested events to event handlers
- IoT Edge lets you run code on the client side which could be useful for firmware upgrades etc. These are done with the help of Azure IoT edge runtime.

- **Azure Service Bus** is more generalized Event hub. It is the messaging communication channel between the application and the services.
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

### Custom Handlers
- a custom handler is a web server. The web server receives events from the Functions host. You then have an opportunity to write code in your preferred language to respond to the events.
- A message queue is a software component that's used to handle messaging between processes, threads, or applications. A queue can store a message, and workers can fetch the message when it's a good time.


### Azure App Configuration
- Allows to centralize the app settings in one location.
- Tiers - Free and Standard
- Has feauture toggle, which integrates with the source code currently only with .NET and C#

### Microsoft Graph API
- Exposes REST API and SDK to access data from or pogrammatically access
    - Microsoft 365 core services
    - Enterprise Mobility and Security Services
    - Dynamic 365 Business Central
    - Windows 10 services
- Microsoft graph connector
    - Simple way to bring data to the graph from the services
- Microsoft graph data connect
    - Way of storing data 

### Azure API Management
- Integrates existing backend services into modern API gateways.
- **Product** is logical grouping of APIs.
- **Groups** used manage the visibility of product to developer
    - **Administrators**, full access. Manages the APIs and access.
    - **Developer**, user with the access to the developer's portal with permissions to build applications. Builds application on top of the APIs.
    - **Guests**, Reading permission to some services
    - Can also create custom groups, external groups in an Associated AAD tenant.
    - APIM does not create API, but creates facades for your APIs
- Gateway, is where your API calls are received, and policies are applied to incoming requests and outcome responses.
- APIM policies allow you to change the behaviour at multiple stages of an endpoint's request lifecycle.
    - Examples - Access Restriction Policies, Cross Origin Policy
    - Policies can be applied at
        - Inbound request
        - Backend - before requests reach your backend
        - Outbound - before sending response back to client
        - Error - when a request encounters an error
- Cloud Service that is used to publish, secure, transform and maintain the API.
- Comping mutliple application exposing APIs and functions into a single entry point.
- We can use API management to forward the requests.
- **OpenAPI** is the set of specification and standard to implement RESTful APIs. **Swagger** is the tool for implementing the OpenAPI specification. **WADL** and **WSDL** are other standards.
- Caching could be achieved in two different ways - BuiltIn and External.

### DAPR (Distributed Application Runtime)
- Provides APIs that simplify microservice connectivity.

### Azure Event Grid 
- It is a Service that allows you to manage event routing from any source to any destination.
- ![image](https://user-images.githubusercontent.com/36666451/198816025-6addf3a3-6df3-42e9-86a9-0108940cb33d.png)
- Event grid is divided into two categories 
    - Event Sources - services that emit data
    - Event Handlers - services that receives data, and event grid sits in between.

### Azure Event Hub
- Event hub is an ingestor that can consume millions of events from anywhere and process them in realtimeor micro-batching.
- ![image](https://user-images.githubusercontent.com/36666451/198817026-93100766-877a-4e73-88dd-86616a104d64.png)
- **Auto-inflate** feature automatically scales the number of throughput to meet your changing needs.
- **Event-hub Capture** is the easiest way of capturing the streaming data into azure and enables you to focus more on the data processing part.
- Event hub kafka compatibility is alternative compatible with the Apache kafka producer and consumer APIs for version 1 and above.
![image](https://user-images.githubusercontent.com/36666451/200185183-65859d58-8a06-4a98-bddd-42abd5e10ff1.png)


## Queue Storage

### Azure Storage Queue
- Simple service to store messages.
- Can handle millions of messages, but no order guaranteed
- Unlimited Queues, Unlimited Concurrent Clients
### Azure Service Bus
- Broader messaging service that supports queuing, pub-sub, and more advanced integration patterns.