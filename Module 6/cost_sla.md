#### Plan and manage cost 

- TCO (Total cost of ownership)
    - estimates cost saving on cloud and give cost comparison between on-premise and cloud
    - Operational costs include electricity, network maintenance, and IT labor.
    - How does it work?
        - Step 1 : Define the workloads
            - Server, Database, Storage and Networking
        - Step 2 : Adjust Assumptions & Step 3: View the TCO report
            - On-premise software licensing, which can be reused on the Azure and whether there is a need to replicate your storage
                to another Azure region for greater redundancy. 
            - This assumption may lead to following cost in the on-premise settings
                - Electricity price, Hourly pay rate for IT administration and Network maintenance cost
    
- How can you purchase Azure services ?
    - Through an Enterprise Agreement
        - Useful for large customers such as a Company or an Organization
    - Directly from web
        - Just like we do. From Azure portal.
    - Through Cloud Solution Provider
        - CSP is a Microsoft partner  who helps you build  solutions on top of Azure.
    
- Types of azure services
    - Free
    - Pay as you go
    - Members offer
    
- Factors affecting cost 
    - Resource Type
        - For example, with a storage account you specify a type (such as block blob storage or table storage), 
          a performance tier (standard or premium), and an access tier (hot, cool, or archive). 
          These selections present different costs.
    - Usage meter
        - Apart from the base price of the resource, you pay as per your usage of a particular resource. For example, 
        VM can be charged based on Overall CPU time, Time spent with the public IP address and incoming and outgoing
          network traffic, disk size and amounts
          
    - Resource usage
        - Deallocating a VM means that the VM is no longer running. 
          But the associated hard disks and data are still kept in Azure. 
          The VM isn't assigned to a CPU or network in Azure's datacenter, so it doesn't generate the costs associated with compute time or the VM's IP address. 
          Because the disks and data are still stored, and the resource is present in your Azure subscription, you're still billed for disk storage.
        - Deallocating a VM when you don't plan on using it for some time is just one way to minimize costs.
    - Azure subscription type
    - Azure marketplace
        - Can also purchase various solutions and services from third party provider.
    - Location
        - Different location may have different association price
    - Billing criteria
        - inbound traffic is free of cost 
        - outbound traffic has price
        - Billings zones as well

- **Azure Advisor** identifies unused or underutilized resources and recommends unused resources that you can remove. 
  This information helps you configure your resources to match your actual workload.

- Can you spending limits to avoid overrunning the budget. Spending limits can be configured.
- Can make use of **Azure Prepay**, which provides discounted prices on certain Azure services, it can save you as compared pay-as-you-go model

- Choosing low cost locations and regions can help as well.
- Make use of Azure Cost Management and Billing, which are free service can help better understanding the expenditure on the Azure services.
- Tag to categorize different expenses related to particular department in the organization or types of resources.
- Resizing resources if underutilized such as VMs to save compute cost
- Deallocate VMs in off hours - Azure Advisor identifies unused or underutilized resources and recommends unused resources that you can remove. This information helps you configure your resources to match your actual workload.
- Delete unused resources
- Migrate to IaaS to PaaS services 
- Save on licensing cost
    - Choose cost-effective OS
    
#### Service level agreement 
- It is a formal agreement between service company, and the customer includes uptime as well.
