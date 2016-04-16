# MeanPeriod5

#### Name attributes of HTTP protocol makes it difficult to use for real time systems.

One of the core principles of the HTTP protocol, is the Request - Response model.
A client sends a request to the server and the server then comes with a appropriate response.
This is a great construction for a traditional website where the client do an action and gets a response back.
Since HTTP is stateless, every single request must have some information about what it want to do, where it should be done and who is doing it and so on.
All this information that needs to be send every time, adds up to alot of bytes which affects the speed of the request - response time.

![HTTP]


#### Explain polling and long-polling strategies, their pros and cons.

##### Polling
The client sends a request for example every 5th second and the server then sends back the response. If there's no new information for the server to send back, it will simply just send back an empty response.
Pros: It's very simple to setup, and since it's just XMLHttpRequests, every modern browser supports this.
Cons: There's alot of traffic because of the number of requests sent to the server.

![Polling]


##### Long-polling
The client sends a request, the server then waits until there's new information before it sends back the response. When the client gets the response, it then immediately sends another request to the server.
Pros: You are notified WHEN(And only when) the server gets new information. Since it's just XMLHttpRequests, every modern browser supports this.
Cons: A bit more complex to setup, and a bit more intensive on the server, since it would have to keep the connection open while it's waiting for new information.
![Long-polling]

#### What is HTTP streaming, SSE (Server sent events)?
The client sends a request using regular HTTP. The server can then send back an event to the client when there's new information without closing the connection.
Pros: Real time traffic from server to client. Uses HTTP for the responses, so no need for a new protocol.
Cons: Doesn't provide CORS (yet). Not supported by IE or Edge.

![HTTPStreaming]

#### What is WebSocket protocol, how is it different from HTTP communication, what advantages it has over HTTP?
WebSockets makes it possible to have a really fast real time system. Instead of sending overhead(Header, cookies and so on) every time, it only gets sent on the initial request.
From there on, the communication is no longer using the HTTP but TCP. This allows really small and low latency communication. Both the server and client can communicate back and forth, so there's no request - response pattern anymore. 

Pros: Real time traffic from server to client AND from client to server. CORS is possible.
Cons: Not all browsers support websockets yet.

![WebSockets]

#### Explain what the WebSocket Protocol brings to the Web-world.
WebSockets makes it possible to have a really fast real time system. Instead of sending overhead(Header, cookies and so on) every time, it only gets sent on the initial request.
From there on, the communication is no longer using the HTTP but TCP. This allows really small and low latency communication. Both the server and client can communicate back and forth, so there's no request - response pattern anymore. 

Pros: Real time traffic from server to client AND from client to server. CORS is possible.
Cons: Not all browsers support websockets yet.

#### Explain and demonstrate the process of WebSocket communication - From connecting client to server, through sending messages, to closing connection.
TODO

#### What's the advantage of using libraries like Socket.IO, Sock.JS, WS, over pure WebSocket libraries in the backend and standard APIs on frontend? Which problems do they solve?
There are multiple reasons of why it can be helpful to use a library for handling the websockets:

##### Fallbacks
If the client browser do not support websockets, there are fallbacks that will give almost the same communication as websockets. That could be ajax long polling.

##### Browser Inconsistencies
Not all browsers are built the same, and therefore they also have different implementations of some functions. By using a library, it wraps the browers functions, so you no longer have to care about how the browser 
does it, but only how to do it with the library.
It also makes it possible to use the same syntax on frontend as on backend. 

##### Extra features
Depending on what library you use for websockets, there are often extra features available that are not in the regular websocket api, such as different "Rooms"/"Namespaces" which allows you to have diffent endpoints or paths for your incoming data. Most libraries also have auto-reconnect if the connection is lost.

##### Popular
Libraries like Socket.IO are really popular and therefore it's often easier to get support for those, than for the pure websocket version.



#### What is Backend as a Service, Database as a Service, why would you consider using Firebase in your projects?
Todo


#### Explain the pros & cons of using a Backend as a Service Provider like Firebase.
Todo

#### Explain and demonstrate “three-way data binding” using Firebase and Angular
Todo

#### Explain and demonstrate the difference between the simple chat system in your own WebSocket + Node.js backend vs. Firebase.
Todo



[HTTP]: http://i.imgur.com/qRk5AzD.png "HTTP"
[Polling]: http://i.imgur.com/Nf7V4Rv.png "Polling"
[Long-polling]: http://i.imgur.com/RaYapa0.png "Long-Polling"
[HTTPStreaming]: http://i.imgur.com/xC9gigZ.png "HTTP-Streaming"
[WebSockets]: http://i.imgur.com/uXlugH1.png "WebSockets"
