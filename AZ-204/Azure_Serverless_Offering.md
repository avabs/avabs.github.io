#### Secret in Github Webhook
-When your secret token is set, GitHub uses it to create a hash signature for each payload. This hash signature is passed along with each request in the headers as x-hub-signature.

When your function receives a request, you need to compute the hash using your secret, and ensure that it matches the hash in the request header. GitHub uses an HMAC SHA1 hex digest to compute the hash, so you must calculate your hash in this same way, using the key of your secret and your payload body. The hash signature starts with the text sha1=.


##### Change feed
- Azure Cosmos DB exposes a "change feed". The change feed support in Azure Cosmos DB works by listening to a database container for changes.


#### SignalR
- SignalR is an abstraction for a series of technologies that allows your app to enjoy two-way communication between the client and server. SignalR handles connection management automatically, and lets you broadcast messages to all connected clients simultaneously, like a chat room. You can also send messages to specific clients. The connection between the client and server is persistent, unlike a classic HTTP connection, which is re-established for each communication.

- SignalR could use Websockets API by default for HTML5 application, Server Sent Events(Event Source) and Ajax in this order.

- When you copy files to a storage container named $web, those files are available to web browsers via a secure server

#### Azure API Management

- Cloud Service that is used to publish, secure, transform and maintain the API.
- Comping mutliple application exposing APIs and functions into a single entry point.
- We can use API management to forward the requests.

#### Custom Handlers
- a custom handler is a web server. The web server receives events from the Functions host. You then have an opportunity to write code in your preferred language to respond to the events.
- A message queue is a software component that's used to handle messaging between processes, threads, or applications. A queue can store a message, and workers can fetch the message when it's a good time.
