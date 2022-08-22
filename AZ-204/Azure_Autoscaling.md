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

### Azure Availability Sets
	- Azure consists of racks upon racks of the server and, each rack could be a **Fault Domain**. Availability Sets distributes workload mutliple Fault Domains. 
	- Grouping VMs in an availability sets also gives the Windows Azure Fabric Controller (FC) the information it needs to intelligently update the host OSs that your guest VMs are running on. Without availability sets the FC would have no idea that two machines were serving the same purpose and could reasonable take them both down for host OS updates.
	- An Availability Set also makes use of Update Domains. This allow you to determine how many of the workloads are down at any given time. 
	- You can set a priority order for shutting down the VMs and the number of update domains determines how many machines will be involved in the shutdown. 
	- Reference - https://www.softnas.com/docs/softnas/v3/html/azure_availability_sets.html