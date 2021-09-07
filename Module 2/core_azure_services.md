### Azure Compute Services
- Azure VMs
- Azure Container Instances
- Azure App Services
- Azure Functions


#### Virtual Machines
- VMs are IaaS. Just like a physical computer. Better when we need total control over OS and network.

#### VMs Scale sets
- Set of indentical VMs, helpful when autoscaling is required
- Can provide highly available environment for an app/service since load can be shared among identical VMs

#### Container & Kubernetes
- Lightweight, virtualized application environment
- Basically can run multiple instances of such on single host machines
- Single Host - VMs - Single Instance
              - Container - Multiple instance
                - Virtualises the OS instead of Hardware like VMs
- Container Orchestrator
    - Azure Container Instance - PaaS Directly maintain a container
    - Azure Kubernetes Service (AKS) - Kubernetes

#### App Service
- Basically PaaS
- PaaS focuses more on the application management, deployement rather than configuration of OS
    - Web app
    - API app
    - WebJob - a script/trigger
    - Mobile apps

#### Functions
- Basically can help in communciation with other Azure services


#### Azure Batch

- Large scale parallel and high performance computing 
    - Starts a pools of VMs
    - takes a job
    - requeues if any failures 
    - scales down once works completes


#### Azure Functions

- Serverless Computing 
    - Abstraction fo the server, infrastructure and OS 

- Event-driven scale
    - Timer
    - Trigger/API or weebhook
- Micro billing
    - Pay as per the usage