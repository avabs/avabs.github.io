#### Availability Zone
- These zones are logically and physically seperate zone within an Azure region having a dedicated power, network, cooling. 3 zones are supported within an Azure region. Not all azure regions have availability zones.

#### Availability Sets
- Every VM in the an azure data center will be placed in a different rack meaning it would have different physicla server, storage, network device, it is called Availability Set. 
- If whole data center goes down then your Availability sets will be gone too.

#### VMSS
- The VMSS lets you create and manage load balanced virtual machines in a group. 