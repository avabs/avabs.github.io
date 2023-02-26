### Azure Content Delivery Network (CDN)
- Putting content in the edge servers which could be fetched by user with lesser latency.
- When requesting to origin server, origin server will forward the request of the user to point of the presence location which are closer to user.	


### Azure Front Door
- Traffic Manager
- Traffice Accelarator
- Global Load Balancer
- CDN
- ![image](https://user-images.githubusercontent.com/36666451/198328338-8f05e594-fc2e-487e-a6f8-33fd61f30698.png)

Features
- Caching, like CDN
- Resiliecny, ditribute traffic between multiple or different azure regionss
- Cookie-based session affinity
- Health probe, determines the healthiest and closest backend to client request
- Web Application Firewall, protecting your backends from malicious attacks and vulnerabilites
- URL Redirect
- URL Rewrite
- ![image](https://user-images.githubusercontent.com/36666451/198330537-6f46e6de-9b5b-4157-82b0-c0c355b3475c.png)

Tiers
- Standard (Delivery Optimized)
- Premium (Security Optimized)

Routing 
- It's the path that a HTTP request takes to reach to the backend
- ![image](https://user-images.githubusercontent.com/36666451/198331385-13872c0e-6eb5-4aaa-b528-1d9dc0444c2a.png)
- Traffic Routing Available 
    - Latency
        - Requests are sent to lowest latency backends acceptable within a sesitivity range
    - Priority 
        - Requests are send based on a user-defined number
    - Weighted
        - Requests are sent acc to weight coefficient
    - Session Affinity 
        - Session request from the same end user gets sent to the same backend

Origin 
- It is the endpoint of the backend

Origin Groups
- It is the group of backends
- Origin must belong to a origin group
- This allows you to apply 
    - Health Probes - health of your origin
    - Load Balancing Settings - the balancing of your origins

Health Checks
- Check for the healthy response from the backend (HTTP Response code - 200 status)

Custom Domain Names
- Can associate multiple Custom domain names with an Azure Front Door profile

Endpoint Manager
- Provides an overview of the endpoints you've configured for your Azure front door 

Routes 
- A route maps your domains and matching URL path patterns to a specific origin group

Traffic Accelaration
- Connecting user to edge location
- Takes direct path


### Azure VPN
- VPN is a sec encrypted secure tunnel/channel of the communication between parties. 
- **Site to Site** - Connects one entire site to another and it is always on. 
    - IPSec is a framework to establish secure channel between routers.
- **Remote Access** - So this is how we connect to our corporate network because we could be anywhere. 