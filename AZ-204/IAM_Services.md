### Azure AD
- It is identity and access management service, which helps your employees sign in and access resources.
- Allows user to access
	- External Application 
	- Offcie 365 and other saas application
	- Interal Applications
	- Cloud application deployed 

- 4 editions of the Azure AD
	- Free - MFA, SSO, Basic Security and Usage Reports, User Management
	- Office 365 Apps Company Branding, SLA, Two Sync between On Premise and Cloud
	- Premium 1 Hybrid Arch, Advanced Group Access, Conditional Access
	- Premium 2 Identity Protection, Identity Governance
- Active Directory is the on-premise component and it is somewhat parent of Azure AD

- AD terminology
	- ![Screenshot from 2022-10-22 01-42-00](https://user-images.githubusercontent.com/36666451/197324003-1f612d0c-8258-49e0-83e0-0cdd8d0c7288.png)

- AD Tenant
	- Represents an organization
	- It's a dedicated Azure AD Service instance.

- For ways to assign access rights 
	- Direct Assignment
	- Group Assignment
	- Rule based assignment
	- External Authority Assignment

### AD Domain Services 
	- Provides domain services such as Domain Joins, Group Policies, LDAP, Kerberos/ NTLM Authentication
	- You can use these services without need to deploy, manage or patch the domain controllers.
	- This is useful when moving into Azure AD and some domain services are not supported.	
	- Let you join the VM to a domain without having to deploy or manage different domain controller.
	- Provides following services 
		- Domain join
		- Group policy

### Azure AD Connect
	- It's a hybrid service to connect your on-premise Active Directory to your Azure Accounts
	- PHS (Password Hash Synchronisation)
		- Sign in Method
		- This is accopmlished by synchronising the hash of the hash of user's on prem AD password on the cloud
	- PTA (Pass Through Authentication)
		- PTA actually authenticates user againsgt the on-prem AD hence leverages on-prem password policies.
		- SSO
		- Works with MFA as well.
		- Secure than PHS since password is not shared with cloud or stored in the cloud.
		- Uses an agent that needs to be installed on the on-prem site.
	- Federation
		- Collection of the domain with an established trust.
		- Ensures that all user authenication happens on the on-prem.
	- Health Monitoring - Robust monitoring and central location for both cloud and on-prem
	- Synchronization - Ensuring that on-prem and cloud data matches		

### SSO 
	- SSO methods
		- SAML
		- Password based
		- Linked
		- Disabled
		- Integrated Windows Authentication
		- Header-based

### Azure AD B2B
	- AD can be used with external partners,even if they don't use Azure AD. Basically allows an user from other organization as guest user in organization data and application

### Azuer AD B2C 
	- Allows organization to control how customers interact with the application.
	- This provides abilities to configure several identity provider (idps). IDPs are basically services that provides authenticated user identities and 
security tokens.

### Azure AD Privileged Identity Management (PIM)
	- Authorizations of user within Azure, Azure AD and other services as well.

### Managed Identities for Azure Resources
	- Allow to access azure service/resource which supports Azure AD without having to store the secret in the code (roughly).

## Roles in Azure 

### Azure Roles
- RBAC System and built on top of ARM
- Two types of roles
	- BuiltIn
	- Custom
- Role Assignment is consists of these three elements
	- Security prinicipal
		- could be user, group, service principal, managed identity
	- Role definition
		- Collection of the permission
	- Scope
	- Set of resources that access for the Role Assignment applies to. 


### Classic Administrators
- This is original role system
- It has three types of Role
	- Account Administrator - Billing owner fo the subscription. Has no access to azure portal.
	- Service Administrator - Same access as user assigned the Owner role at subscription scope. Full access to Azure portal
	- Co-Administrator - same access of a user who is assigned the Owner role at the subscription


### Azure AD Roles
- Azure AD roles are used to manage Azure AD resources in a directory.
	- Create or edit users
	- Assign admin roles to others
	- Reset user passwords
	- Manage user license
	- Manage domains
- Built in Azure AD Roles
	- Global admin - Full Access to everything
	- User admin - Full access but limited to user management
	- Billing admin - makes purchases, manage subscriptions and support tickets
- You need p1 or p2 for custom roles


### Azure Policies
- Ensures the compliance of the resource whereas Azure Role deals with the access to the resources

### Cheatsheet
![image](https://user-images.githubusercontent.com/36666451/197333576-114c9fc1-0303-417e-9420-4e61132d55a5.png)