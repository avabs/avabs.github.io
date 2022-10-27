### Azure Monitor 
- It provides System level monitoring. Application Insights could be used in order to acheive one-to-one monitoring with application.

### Azure Analytics 
- Similar to Splunk and ELK stack.


### Azure Health 
- First line of the defense for identifying the problems with the azure resources.
- Azure Status - provides information on the global issue, not specific to your account.
- Azure Service Health - Just like Azure Status but specific to your account.
- Azure Resource Health - More granular level of the details regarding an Azure Resource.

### Azure Advisor 
- Information and suggestion on Security, Availability, Performance and Cost.

### Azure Activity Log 
- Records events using event data from Azure Resource Manager.


### Azure Network Watcher 
- Monitors what happens between different resources. Analyzing network events.

### Azure Security Center 
- Centralized dashboard for the security of the infrastructure.'

### Other Services
- Azure Log Analytics is where all the logs are stored for the analysis
- Azure Automation is the service which lets you automate few mundane tasks such as the update management, patching of the VMs.


### Azure Application Insights
- It is Application Performance Monitor. It does monitoring and management of performance and availability of the software apps.
- It is sub service of Azure monitor
- Examples of APM - Datadog
- ![image](https://user-images.githubusercontent.com/36666451/198342565-142c4886-bf40-4cf6-b666-46a5095f07c7.png)

- **Open Telemetry**
    - It is collection of open-source tools, APIs and SDK to instrument, generate, collect, and export telemetry data.
    - It standardizes the way telemetry data (metrics, logs and traces) are generated and collected.
    - **Wire Protocol**
        - A wire protocol refers to a way of getting data from point to point. Eg. SOAP, AMQP
    - Azure supports OTEL as an alternative to Azure Analytics SDK for instrumentation

- Intrumentation
    - You instrument your application by adding Azure Application Insights SDK and implementating traces.

- Auto-Intrumentation. Instrumentation of the application without changing the code
