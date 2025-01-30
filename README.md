# ChatApplication

**COMPANY**: CODTECH IT SOLUTIONS

**NAME**: LOGESWAR S

**INTERN ID**: CT08JFB

**DOMAIN**: JAVA PROGRAMMING

**BATCH DURATION**: JANUARY 5th,2025 to FEBRUARY 5th, 2025

**MENTOR NAME**: NEELA SANTHOSH KUMAR

This chat application is a client-server system developed using Java's Socket Programming and Multithreading concepts. The application allows multiple clients to connect to a server, send messages, and receive messages from other clients in real-time. Here's a breakdown of how each component works:

Components
Server:

The server listens for incoming client connections on a specific port.
Upon accepting a client connection, the server creates a new thread (using the ClientHandler class) to handle communication with that specific client.
Each client can send a message to the server, and the server then broadcasts that message to all other connected clients.
The server also manages a list of active clients and ensures that if a client disconnects, they are removed from the active list.
Client:

A client is a Java application that connects to the server using the specified IP address and port.
The client sends messages to the server and can receive messages from the server using separate threads:
One thread listens for incoming messages from the server.
Another thread reads user input from the console and sends it to the server.
Clients are able to view messages broadcasted by the server, which can include messages sent by other clients.
Key Features
Multi-threading:

The server uses multithreading to handle multiple clients simultaneously. Each client is handled by its own thread (ClientHandler), which ensures that communication can occur without blocking the server's main thread.
The client also uses multithreading to listen for incoming messages while simultaneously allowing the user to input new messages.
Broadcasting Messages:

When one client sends a message, the server broadcasts that message to all connected clients (except the sender). This allows all clients to see the messages in real-time.
Socket Communication:

The application uses Java Sockets (ServerSocket and Socket) to establish communication between the server and clients. The server listens for client connections, and clients connect to the server using the server's IP address and port number.
How it Works
Server Side:

The server starts by creating a ServerSocket to listen on a specific port (e.g., 12345).
When a client connects, the server accepts the connection and creates a new ClientHandler to communicate with that specific client.
Each ClientHandler runs in a separate thread and listens for messages from its corresponding client. When a message is received, the server broadcasts it to all other connected clients.
The server maintains a set of active clients to keep track of who is connected. It also ensures that when a client disconnects, the client's handler is properly removed from the active list.
Client Side:

A client connects to the server using the server's IP address and port number.
The client is capable of sending messages to the server, and these messages will be broadcast to all other connected clients.
The client also listens for incoming messages from the server and displays them on the console.
The client allows the user to input messages via the console. As the user types a message and presses "Enter," the message is sent to the server.
Interaction Flow
Server Starts:
The server starts and listens for incoming client connections.

Client Connects:
A client connects to the server using its IP address and port number.

Client Sends Message:
Once connected, the client can send messages to the server by typing text into the console and hitting "Enter."

Server Broadcasts Message:
The server receives the client's message and broadcasts it to all other clients that are currently connected.

Client Receives Messages:
All connected clients, except the sender, receive the broadcasted message and print it on their console.

Client Disconnects:
When a client disconnects (either by closing the console or exiting), the server will remove that client from its active list and stop listening to their socket.

**OUTPUT**:
# ClientSide
