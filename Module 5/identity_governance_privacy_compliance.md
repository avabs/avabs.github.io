### Identity, Governance, Privacy and Compliance Features

#### Azure Active Directory
- Provides identify service that enables your user to sign in to access both microsoft cloud apps and cloud applications 
that you develop
- It provides 
    - Authentication
    - SSO
    - Application Management
    - Device management
    
- It can help to secure both internal and external resources such as microsoft 365, Azure portal and SaaS apps
- SSO, a user can remember only one credential and use it for other apps as well
- Azure AD and Active Directory can be connected via azure aD Connect
- Conditional Access 
    - During sign-in, Conditional access collects signals from the user, makes decisions based on that whether
    allow the access or deny
      
#### Build a Cloud Governance Strategy on Azure
- Governance is general process of establishing rules and policies
- Azure Role based Access control (RBAC)
    - Rules are applied to scope and scope consists of 
        - A Management Group
        - A Single Subscription
        - A Resource  Group
        - A Resource
    - It is used against AZ resources that passes though Azure Resource Manager
    - It doesn't apply access control in the application
    - Resource lock prevents accidental deletion or changes - CanNotDelete and ReadOnly
    - In order to delete a resource, lock has to taken out first
    
- Tags can help to manage resources, cost management and other

#### Azure Policy
- Lets you create, assign and manage policies that control your resources
- Personla and group related policies are called Initiatives
    - Initiative is way of grouping related policies into one set
    - Can help you track compliance state of the product
- Can control creation of a resource or size of the resource as well as can point out non-compliant resource.
- SKU - Stock-Keeping Unit
- Examples
    - Allowed VMSKU
    - Allowed Locations
    - MFA
    - CORS should not be allowed
    
- Policy assignment to a scope 
    - Child inherits the policy of upper level scope, however it can be exempted


- **Azure blueprint** can be helpful for responsible set of governance tools and standard azure resources
    - Role, policy assignments
    - ARM templates
    - RG
    
- ISO 27001 : A standard applies to the security of IT systems

- Cloud Adoption Framework : helps you create and implement the business and technology strategy


#### Compliance terms and requirements

- Global US Government Industry Regional 
- CIJS Security Policy
- Cloud Security Alliance STAR certification
- DPA - Data Protection Addendum
- PCI DSS

- Azure Government is a separate instance of the Microsoft Azure service
- Azure Chine 21ViaNEt
    - Physically separates instance a cloud services located in China
    - Services are still same
    