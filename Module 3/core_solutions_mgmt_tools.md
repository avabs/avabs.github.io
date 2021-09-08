### Azure Core Solutions and Management tools 

- In IOT, Sensors captures data and relays such information for data analysis.

- **Azure IOT hub** is a managed service that can acts as a central hub for bi-directional communication between application and device.
    - Lets you connect, monitor and manage your IOT devices
    - Sending alerts, notification and pushing firmware updates to the device
 
- **Azure Sphere** 
    - End to end and Highly secure IOT solution for the customer.
    - Has hardware and OS, built-in communication and security features for internet connected devices
    - Has Micro controller, OS and Signals from attached sensors
    - OS (Customized Linux OS)
    - Azure Sphere Security Service (AS3)
    - Dashboard can be created using IOT HUB Restful API

- **AI**
    - Azure Machine Learning
        - Platform to predict
        - Test, train and deploy
        - access it via a web based API
    
    - Azure Cognitive Service
        - Prebuilt machine learning models
        - Enables app to see, hear, speak, understand and even begin to reason
        - OCR, Sentiment Analysis
    
    - Azure Bot Services
        - Conversational Purpose
    
- **Azure DevOps** 
    - Azure Repos 
        - Centralized soruce code repo
    - Azure Boards
        - Agile Project Management
    - Azure Pipelines
        - CI/CD pipeline automation tool
    - Azure Artifacts
        - Repository for hosting artifacts
    - Azure test plans  
        - Automated test tool
    - GitHub and GitHub Tools
    
- **Azure Dev Test Labs***
    - Provides automated way of managing the process of building, setting up and tearing down VMs that contain builds of software projects
    
#### Configuring and managing azure environment

- Two broad categories of management tools : Virtual tools and code based tools
- Code based tool is useful when setting up large deployment

- Approach to managing hardware and cloud resources, which developers use when they write application code is referred to
  as "Infrastructure as Code"
  - Imperative 
        - Coding Individual Step
  - Declarative
        - Details only desired outcome
        - It allows an interpreter to decide how to best achieve that\
  - Azure Resource Manager templates 
        - JSON file
        - It can have both Azure PowerShell and Azure CLI scripts
    
#### Monitoring Services

- **Azure Advisor**
    - Evaluates resources and provides recommendation to improve reliability, security, performance, cost and Operational Excellence
    
- **Azure Monitor** 
    - Taking actions on the logging data and metrics
    
- **Azure Service Health**
    - Service issues such that outage in the region
    - Planned maintenance
    - Health advisory 