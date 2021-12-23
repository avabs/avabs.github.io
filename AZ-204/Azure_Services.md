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