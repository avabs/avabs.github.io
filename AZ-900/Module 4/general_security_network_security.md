### General Security 

- **Azure Security Center**
    - Provides visibility of the security postures across all the cyber services both on Azure and on-premise
    - Security postured refers cybersecurity policies and controls as well as how well you can predict, present and 
    respond to the security thread.
    - Detect, analyze and apply new security settings to the azure resources
    - use Ml to avoid installing malware application
    - Protect against threats
        - Just in time VM access : blocks traffic by default, waits for admin approval
        - Adaptive app control : application running allowance is controlled
        - Adaptive traffic/network hardening : SC monitors the internet traffic patterns of the VMs
        - SC can make recommendation on teh Network.
        - File integrity monitoring is also provided 
        - Workflow automation uses Azure logic apps and security center
        - SC is centralised security portal
    
- **SIEM** (Security Information and Event Management) aggregates security data from many sources.
    - It provides capabilities for threat detection and response
    - **Azure Sentinel** is SIEM 
        - Collects cloud data
        - Detect previously undetected threats 
        - Investigates threats with AI
        - Responds to incidents rapidly
        - Connect datasource which sentinel can analyse
        - Connector is also available for non-microsoft services such as AWS cloudtrail     
        - Connects to other datasource as well
        - Built in analytics
            - templates based analysis - template are provided by Azure, or it can be custom as well
    
- **Azure Monitor Playbooks** automates response to the threat

- **Azure key vault** 
    - Centralized service to store the secrets 
    - Manages secrets, encryption and certificates SSL/TLS etc.
    
- Azure dedicated host provides a physical unit to run your VMs

### Network Security 

#### Defense in depth

- Physical Security : First line of defense to protect computing hardware 
- Identify & Access : Stop unauthorized access - SSO, MFA
- Perimeter : DDoS protection, firewalls 
- Network : Limits connection between resources though segmentation and access control
- Compute : Secure access to virtual machines, endpoint protection
- Application : Apps are safe and free of security vulnerabilities
- Data : Controls access to business and customer data

**Security Postulates** 
    - Confidentiality 
        - Principle of the least privileges
        - Includes protection of user passwords, email access and access control
    - Integrity 
        - Prevent unauthorized access to info
        - data sent in a channel is checked on the basis of their hash if it is not compromised

#### Protect Virtual network by using Azure Firewall
- Firewall is a network security device that monitor incoming an outgoings network traffic decide whether to allows
or block specific traffic
- Managed cloud based firewall 
    - It is a stateful firewall, analyses the complete content of a network connection
    - uses static public IP for subnet resources
    - Built in high Availability 
    - Unrestricted cloud scalability 
    - Inbound and outbound filtering rules
    - Inbound Destination Network Address Translation (DNAT) support
    - Azure monitor 
    - Network rules that defines 
        - Source address
        - Protocol
        - destination port and 
        - destination address
    
- Web Application Firewall : Azure FrontDoor, Azure CDN


#### Protect from DDoS attacks
- Understands between legitimate and attacking users and blocks the unauthorized access to apps
- Types of attacks
    - Volumetric :  No of requests
    - Protocol Layer : weakness in layer 3 and 4 
    - Resource Layer/App layer : You'll require WAF to protect against L7 attacks
- NSG
    - Filter traffic to and from Azure resources
    - It is an Internal firewall

- Combined services
    - NSG and Azure Firewall
    - WAF and Azure Firewall
