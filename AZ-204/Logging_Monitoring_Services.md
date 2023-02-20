### Azure Monitor 
- It provides **System level monitoring**. **Application Insights** could be used in order to acheive one-to-one monitoring with application.
- It is an comprehensive solution for **collecting**, **analyzing**, and **acting** on telemetry from your **cloud** and **on-premise** environments. 
- Many azure services by default sends telemetry data to Azure Monitor.

- **The Pillars of Observability**
    - ![Screenshot from 2022-10-27 22-35-58](https://user-images.githubusercontent.com/36666451/198354284-dfcebea4-4a8c-42ff-aa02-5ea6523f3cce.png)

- Sources of the common monitoring data
     - Application 
        - Instrumentation Package to collect application insights
        - Availability test responsiveness of the application from different location on the internet
     - OS, On the guest
        - Diagnostic Extension collects performance counters stores in Metrics
        - Log Analyhtics Agent for comprehensive monitoring
        - Dependency Agent collects discovered data from process running on VM and external process dependencies.
     - Azure Resources
        - Metrics
        - Resource logs
     - Azure Subscription
        - Service Health - provides health of the services in your subscription
        - Active Directory
     - Azure Tenant
        - Active Directory
     - Custom Sources
        - Instrumentation package
        - Applications

- Two fundamental data stores are 
    - logs --> Azure Monitor Logs
        - Log Analytics is a tool used to edit and run log queries with data in Azure Monitor Logs
        - Query Language is Kusto Query Language, it is based on relation database management systems
    - Metrics --> Azure Monitor Metrics

- Actions on data
    - Insights
        - App, containers, Vms, Monitoring solutions
    - Analyze
        - Metric Analytics, Log Analytics
    - Visualize
        - Dashboard, Views, Power Bi, Workbooks
    - Respond
        - Alerts, AutoScale
    - Integrate
        - Logic Apps, Export APIs


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

- Auto-Intrumentation. Instrumentation of the application without changing the code.
