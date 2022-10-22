### Azure Storage Accounts
- Contains all of your Azure Storage data objects: blobs, files, queue, table and disks
- Azure provides different types of Storage Accounts 
    - General purpose v1 (legacy)
    - General purpose v2
    - Blobstorage (legacy)
    - Block Blob storage
    - File Storage
- These differs by there features 
    - Supported Services - Blob, File, Queue, Table, Disk and Data Lake
    - Performance Tier - Standard (HDD) and Premium (SSD) - IOPS based, higher the IOPS better read/write speeds
    - Access Tier - Hot, cool and archive
    - Replication - Redundancy to the zones
    - Deployment Model - ARM or classic
- **Storage Types**
    - ![image](https://user-images.githubusercontent.com/36666451/197263447-dfdd00c7-489c-461e-afe0-962ddf566e33.png)

#### Azure Storage Services
- Azure provides different storage services. These are all under Azure Storage Accounts
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
    - Hierarchy of the blob - Storage Account >> Container  >> Blob
    - Containers withing blob storage are used to organize the blobs just like directories.
    - Types of blobs supported by AZ
        - Block blobs - contians blocks of data, text and binary data
        - Append blobs - same as block, optimized for append, good for logging output
        - Page blobs - random access files storage
    - Azure also provides immutable objecct storage policy where you will not be able to delete or modify
     
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


#### Azure Blob Storage 
    - Page Blobs
	- Commonly used for virtual hard disks on Azure VM
	- Optimised for read and write - 512 byte
    - Block Blobs
	- Storage large blobs (4.75TB)
	- Blobs could be deleted or updated
    - Append Blobs
	- Optimised for append operation
	- Inseration at the end of the blob only
	- Can not be deleted or updated
    - Moving blobs between Storage Containers	
	- It is not supported natively.
	- It could be achieved with AzCopy tool.
	- Data Movement Library can also help in such operation.
    - Moving blobs between Storage Accounts
	- AzCopy is helpful here.
    - Blob leasing provides ownership of the blob for given time period or indefinitely and it makes sure that blob is read-only during lease period
    - Tiers in decreasing order of the cost - Premium - Hot - Cold - Archive
    - Retention Policies - Time Based & Legal Hold

#### Azure Blob Storage
- Blob storage has capabilities to store unstructured data which 
may contain Binary files or text files.
- Authorising request to Blob storage 
  - Shared key, which is a account key 
  - Shared Access Signature which are token that gets appended to blob urls
  - Azure AD
  - Anonymous read access
- Blob types
  - Block Blob
    - Here blob will be stored as block, where file could replaced
  - Append Blob
    - Log files which are appended at the end could be an example of append blob
  - Page Blob
    - Random read/write possible in this blob type and anywhere in the file. Example - Azure Virtual Machine 
- Azure SDK
  - Collection of the client library.
- Access Tiers 
  - Hot
    - Frequently used data
  - Cool
    - Infrequently accessed data stored for at least 30 days
  - Archived
    - Data that can be archived for at least 180 days.
  - Archived of type 'offline' where hot and cool are of type 'online', so setting a blob to archived will not allow changing the data but properties
    To access data, access tier needs to be converted to hot or cool and process is calledd rehydrating.

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