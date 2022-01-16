### Azure AD
- Allows user to access
	- External Application 
	- Offcie 365 and other saas application
	- Interal Applications
	- Cloud application deployed 

### Azure Domain Services
	- Let you join the VM to a domain without having to deploy or manage different domain controller.
	- Provides following services 
		- Domain join
		- Group policy

### Hybrid Identity (Cloud & On Prem)
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
