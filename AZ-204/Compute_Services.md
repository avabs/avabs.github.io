
### Azure Availability Sets
- Azure consists of racks upon racks of the server and, each rack could be a **Fault Domain**. 
- Availability Sets distributes workload mutliple Fault Domains. 
- Grouping VMs in an availability sets also gives the Windows Azure Fabric Controller (FC) the information it needs to intelligently update the host OSs that your guest VMs are running on. Without availability sets the FC would have no idea that two machines were serving the same purpose and could reasonable take them both down for host OS updates.
- An Availability Set also makes use of Update Domains. This allow you to determine how many of the workloads are down at any given time. 
- You can set a priority order for shutting down the VMs and the number of update domains determines how many machines will be involved in the shutdown. 
- Reference - https://www.softnas.com/docs/softnas/v3/html/azure_availability_sets.html


#### Azure App Service

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

- Azure Container Instances is development and deployment oriented. Provides Hypervisor Isolation, which makes sure that you're organization is not sharing the OS Kernel.

- Azure Kubernetes Service, manage and deploy kuberenetes.

- Azure Container Registry. allows to store and manage container image in the central registry.

- Azure Service Fabric, allows to build and operate always, scalable and distributed apps


#### Multi Stage Builds
- Mutiple docker files could be maintained as single Dockerfile where each dockerfile is a stage.


#### Building Container with Azure DevOps

- Docker images can be pushed to a Registry created using ACR

- Containers are deployed in container groups. Container groups are a similar concept to Kubernetes pods. They are a grouping of containers and run on the same hardware and use the same networking.
