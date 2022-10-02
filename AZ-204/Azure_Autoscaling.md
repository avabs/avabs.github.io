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
