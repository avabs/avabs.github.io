### Describe Azure Core Services

- Basic understanding : Azure is cloud computing services which allows it's users to run there solution on the remote hardware (Cloud) and solution maybe a website, ML models or bunch of VMs
- Basic services are - Computing Power and Storage, and it follows pay-as-you-go pricing model

- Virtualization : 
    - It refers to removing or separating tight coupling of hardware and OS using Hypervisors

- Azure Services are as follows  :
    Compute - eg. adding VMs/Container  
    Network - eg. VPNs adn Load balancing can be one example
    Store - Files, Blobs, Queue and Disks
    Mobile - Build/Deploy/Notifications, usage of cognitive services
    Databases - Open source db tools
    Web - Build/Deploy/Scale web app
    IOT - Connect/Montior/Manage your IOT asset
    Big Data - Run Analytics on Big Data
    AI - Forecast future, behavioural insights
    DevOps - CI/CD


- Azure subscription can be understood like this 
    - at the top level, we have Azure Accout and as we go down Subscription -> Resource group and at the tail it will be resource



#### Public, Private and Hybrid 
- Public clouds are Internet facing and are open to everyones use and hardware of the cloud are managed by the third party
- Organisation have their own cloud and for that they have setup of the hardware resources 
- Hybrid consists of both the types of cloud model. For example - Azure and On-Premise model

#### Cloud Computing Advantages

- #### High Availability
    - No apparent downtime based on the SLA

- #### Scalability 
    - Vertical : Addign more RAMs or CPUs to VMs
    - Horizontal : adding instances of the resources

- #### Elasiticiy 
    - auto-scalable environment

- #### Agility 
    - Building and deploying easily

- #### Geo-distribution & Disaster Recovery
    - Customer will always have best performance
    - Back and data replication



#### Capital & Operationl Expenditure
    - Upfront cost for the hardware or the setup
    - Other is money spent on the maintenance, services and product


#### Computing Models
- #### IAAS 
    - Setting up hardware is already done by the Cloud Provider and then tenant is in charge configuring OS and Network
    - Benefits 
        - No CapEx
        - Agility
        - Management
        - Consumption based model
        - Skills - Making the workload secure and safe
        - Cloud benefits
        - Flexibility 
- #### PAAS
    - Cloud provides manages the configuration and networking resources and cloud tenant deploy there application to the hosting environment.
    - Same benefits as IAAS, however focuses more on the Productivity
- #### SAAS
    - Microsoft office 365, everything is already deployed to cloud.
    - More for the software usage 
- #### Serverless computing
    - Enables developers to focus more on the application development, rest of the configuration are already taken care by the cloud provider


#### Azure Terms
- #### Resource group 
    - Resources are contained into groups that acts as a logical container
- #### Management Group
    - Manages access, poliy and compliance over multiple subscription

    