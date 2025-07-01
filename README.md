COMPANY NAME : CODTECH IT SOLUTIONS

NAME : S NIVILA

INTERN ID : CT04DF2638

DOMAIN : JAVA

DURATION : 4 WEEKS

MENTOR : NEELA SANTHOSH

📡 Task 3: Client-Server Chat Applications

This project is a **Java-based multithreaded chat application** that allows multiple clients to connect and communicate with each other in real-time through a central server. It is built using core Java technologies such as **Java Sockets**, **Input/Output Streams**, and **Multithreading** to demonstrate the fundamentals of client-server communication and concurrent programming.
The goal of this application is to showcase how multiple users (clients) can connect to a server simultaneously and engage in live chat. The server listens for incoming connections and creates a new thread for each connected client, ensuring that all clients can send and receive messages concurrently.
This task involves building a **multithreaded client-server chat application** using Java Sockets. The system includes:

- A `Server.java` program that listens for multiple client connections and broadcasts messages to all connected users.
- A `Client.java` program that allows users to send and receive messages in real-time.

Each client is handled on a separate thread, showcasing how Java can be used to manage concurrency in a networked application. This task simulates real-world chat systems and demonstrates how to maintain active communication between multiple users.

## Features

-  **Client-Server Architecture**  
  The application is structured around a central server that accepts multiple client connections over a socket interface.

-  **Multithreading**  
  The server uses multithreading to manage each connected client, allowing parallel message handling.

-  **Real-Time Communication**  
  Clients can send and receive messages in real-time without delays or message loss.

-  **Console-Based Interface**  
  The interface is simple and text-based, ideal for understanding the flow of communication and debugging.

-  **Graceful Disconnection**  
  Clients can disconnect at any time, and the server handles it smoothly by removing them from the active users list.

---

## Instructions

> • **Build a client-server chat application using Java Sockets and Multithreading to handle multiple users.**  
> • **Deliverable: A functional chat application with a server and multiple clients communicating in real-time.**

---

## File Structure

### 1. `ChatServer.java`

- Initializes a `ServerSocket` on port `1234`.
- Waits for incoming client connections in an infinite loop.
- For each client, a new `ClientHandler` is created and started in its own thread.
- Maintains a static list of all active clients for broadcasting messages.
- Handles username registration, message routing, and client disconnections.

**Key Methods:**

- `broadcast(String message, ClientHandler excludeUser)`: Sends a message to all connected clients except the sender.
- `removeClient(ClientHandler clientHandler)`: Removes a client from the active client list.
- `ClientHandler.run()`: Handles incoming messages from an individual client.

### 2. `ChatClient.java`

- Connects to the server at `localhost:1234`.
- Sends a username as soon as it connects to the server.
- Spawns a background thread to listen to incoming messages from the server.
- Reads user input from the console and sends it to the server for broadcasting.

---

## How It Works

1. **Start the Server:**
   Run `ChatServer.java` to initiate the server on port `1234`.

2. **Connect Clients:**
   Run `ChatClient.java` in separate terminal windows (or different machines using network IPs) to connect clients.

3. **Login with Username:**
   Each client is prompted to enter a username upon connection.

4. **Real-Time Messaging:**
   Messages typed by any client are sent to the server and broadcasted to all other clients in real-time.

5. **Client Exit:**
   When a client exits (Ctrl+C or closes terminal), the server detects the disconnection and updates the active user list.

---

## Technologies Used

- Java SE (Standard Edition)
- Java Sockets (`java.net.*`)
- Java I/O Streams (`java.io.*`)
- Java Multithreading

---

## Use Cases

- Educational purposes to learn socket programming and multithreading.
- Foundation for building more complex messaging systems.
- Base prototype for chatroom-like functionality in enterprise apps or games.

---

## Future Enhancements

- Add GUI support using JavaFX or Swing.
- Support for private messaging and user authentication.
- Persist chat history to a database or file.
- Integration with web services or REST APIs for message logging.

---

## Getting Started

### Prerequisites

- JDK 8 or higher
- Any IDE (Eclipse, IntelliJ, VS Code) or terminal with `javac` and `java` commands

### Compile and Run

**For Server:**
```bash
javac ChatServer.java
java ChatServer
