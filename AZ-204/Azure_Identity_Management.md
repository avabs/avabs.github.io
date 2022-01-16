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
		

