### Azure Storage Account
![image](https://user-images.githubusercontent.com/36666451/197263447-dfdd00c7-489c-461e-afe0-962ddf566e33.png)

### Azure Storage Services
- **Blob storage**
    - Storage for the object, unstructed data such as text and binary.
- **Azure Queues**
    - Provides storage for the messages.
    - A message could be <= 64kb
- **Azure Tables**
    - For NoSQL data
    - Provides storage for key/value data and schema-less design
- **Azure Files**
    - File share system for cloud or on prem.
    - Could be mounted on multiple OSs - Windows, Linux and Mac
- **Azure Disks**
    - Block level storage volumes
    - Provides storage capabilites for the VMs
    - Just like a physical disks - HDD, SDD disks
- Containers could be created in order to further categorize data into these above storage types

#### Azure Blob Storage
- Hierarchy of Blob storage in Azure: **Storage Account >> Container >> Blob**.

- Types of Blobs supported in AZ are: 
    - **Block Blobs** (for storing large data and can be deleted or updated), 
    - **Append Blobs** (optimized for append operations and cannot be deleted or updated), and, 
    - **Page Blobs** (for random access files storage, commonly used for virtual hard disks on Azure VM).

- Azure also provides an immutable object storage policy where objects cannot be deleted or modified. Moving blobs between containers is not supported natively but can be achieved using **AzCopy** or Data Movement Library. Moving blobs between storage accounts can be done using AzCopy.

- Blob **leasing** provides ownership of the blob for a given time period, making the blob read-only during that time. 

- Tiers of Blob storage, in decreasing order of cost, are **Premium, Hot, Cold, and Archive**. Retention policies include Time-Based and Legal Hold. Blob storage can store unstructured data in the form of binary or text files. Access tiers include Hot (for frequently used data), Cool (for infrequently accessed data stored for at least 30 days), and Archived (for data that can be stored for at least 180 days). Archived data is of type 'offline' and to access it, the access tier needs to be converted to hot or cool (process called rehydrating).

- Authorizing requests to Blob storage can be done using **Shared Key** (account key), **Shared Access Signature** (token added to blob URLs), **Azure AD**, or **Anonymous read access**. 

- Blob storage can be accessed using the Azure SDK, which is a collection of client libraries.

- The security principal may be a user, group, application service principal, or Azure managed identity. The security principal is authenticated by Azure AD to return an OAuth 2.0 token. The token can then be used to authorize a request against the Blob service.

#### Azure Files
- Enables file share on the cloud.
- Uses Server Message Block Protocol  (SMB) in order to do so.
- Equivalent of the on-prem file server and could be mounted on the linux, windows and Mac server.

#### Azure Queues
- Provides storage for the message which are used for communication among distributed application, these message could be up to 64kb in the size and AZ Queues are accesible through HTTP or HTTPS connections.

#### Azure Table Storage
- Allows you store thge NoSQL database
- A Table would contians several entities which need not share the same property and table does not enforce any schema on these entities.

#### Azure Managed Disks 
- Azure Managed Disks are used for the VMs.
- Disk Roles 
    - Data - Stores application data
    - OS - hosts the VM's OS and boot volume
    - TEMP - not a managed disk, store pages and swap files

### SAS
- A shared access signature (SAS) provides secure delegated access to resources in a storage account. With a SAS, you have granular control over how a client can access data. You can specify what resource the client may access, what permissions they have to those resources, and how long the SAS is valid. SAS is given to a client who require accesss to resource for short time. 


### Azure Key Vault
- Helps you safeguard cryptographic keys and other secrets used by cloud apps and services.
- Focuses on 
    - Certificate Management
        - Easily provision, manage and deploy public and private SSL certificates for use with Azure and internal connected resources
    - Key Management
        - Create and control the encryption keys used to encrypt your data
    - Secret Management
        - Stores password, token, certs and other secrets
- HSM and FIPS
    - Hardware Security Module
        - Hardware designed to store encryption keys
    - Federal Information Processing Standard 
        - US and canadian goverment standard that specifies the security requirements for cryptographic modules that protect sensitive information
        - HSM that are multi-tenant are **FIPS 140-2 Level 2 compliant**
        - HSM that are single-tenant are **FIPS 140-2 Level 3 compliant**
- Vault stores secrets and keys can be protected by software or **FIPS 140-2 Level 2 validated HSMs**
- Azure Key Vault provides two types of container
    - Vaults
    - HSM Pools
- Pricing Tiers 
    - Standard
    - Premium
        - HSM Backed Keys/ Software backed 
- Keys
    - When creating keys, there are three options
        - Generate - Azure will generate key            
            - RSA (Rivest - Shamir - Adleman) or EC (Elliptic Curve cryptography)
        - Import - Importing a RSA key
        - Restore backup - Restore a key from a backup
    - For Premium, we have options for HSM as well.
    - **Microsoft managed keys (MMK)** are keys managed by microsoft. Not shown in key vault.
    - **Customer Managed Keys (CMK)**  are keys you create in Azure Key Vault. 

- Double encryption
    - Storage Accounts 
        - Infrastructure Encryption 
            - By default, AZ encrypts storage account data at rest, this adds second layer of encryption to the data
    - Azure Disk 
        - Double Encryption
            - Two or more layers of independent encryption layers are enabled to protect against the compromises of any one of the layer.

    - Microsoft has a two layered approach each for Data-at-rest and In-transit
        - Data at rest
            - Disk Encryption using CMK
            - Infrastructure Encryption using platform managed keys 
        - In transit
            - TLS 1.2
            - Additional layer of encryption provided at the infrastructure layer
- China used FIPS - 140 - Level 1 whereas other regions go for level 2 for the secret storage
- Secrets are always encrypted

- X509 Certificate
    - **PKI (Public Key Infrastructure)** 
        - PKI is a set of roles, policies, hardware, software and procedures needed to create, manage, distribute, use, store and revoke digital certificates and manage public-key encryption. 
    - It is a standard defined by Internation Telecommunication Union (ITU) for public key certifications
    - Used with 
        - SSL/TLS and HTTPS
        - Signed and encrypted email
        - Code signing
    - A certificate contains
        - An identity - hostname, organization or individual
        - A public key - RSA, DSA, ECDA etc
    - CA (certificate authority)
        - It issues the digital certificates
        - A trusted third party by owner of the certificate and party relying on the certificate
    - Certificate Formats
        - PEM
        - CER
        - PFX