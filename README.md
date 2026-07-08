# 🧠 Python Multi-Client Chat System with Server Discovery

A beginner-friendly Python networking project that allows multiple users to chat over a network using TCP sockets. This system includes a **Discovery Server** to dynamically provide the chat server IP and port to clients.

Perfect for learning about:
- Python socket programming
- Multi-threading
- Inter-device communication
- Server-client architecture



## 🚀 Features

- 🔍 **Server Discovery:** No need to hardcode the server IP. Clients ask a discovery server for the current chat server IP and port.
- 💬 **Multi-client Support:** Multiple users can join and chat at the same time.
- 🔐 **Private Messaging:** Send messages directly to another user using `@username`.
- 🧵 **Threaded Communication:** Smooth concurrent handling of multiple clients.
- 🧪 **Lightweight and Pure Python:** No external dependencies.



## 📁 Project Structure

```
socket-chat-discovery/
├── server/
│   └── server.py        # Handles both chat and discovery services
├── client/
│   └── client.py        # Connects to discovery server and chats
├── README.md            # Project documentation
├── LICENSE              # MIT License
```



## ⚙️ How It Works

### 📡 Discovery Phase

1. The discovery server runs on a known port (default: `5001`).
2. Clients connect to it and receive the current IP and port (e.g., `192.168.1.29:5555`) of the chat server.

### 💬 Messaging Phase

1. Client connects to the chat server using provided IP/port.
2. User sets a unique username.
3. Messages can be:
   - Sent to everyone.
   - Sent privately using `@username Your message`.



## 🧪 How to Run

### 🐍 Prerequisite

- Python 3.x installed

### 🖥️ Start the Server

```bash
cd server
python server.py
```

This will start both the chat and discovery servers.

### 💻 Start a Client

On the same or different machine (in the same network):

```bash
cd client
python client.py
```

You'll be prompted to enter your username.



## 🔐 Private Messaging

To send a private message to a user:

```text
@lucky Hello,lucky!
```

Only the user `lucky` will receive this message if they are connected.



## 🌐 Network Configuration

Ensure:
- All devices (clients and server) are on the same LAN/Wi-Fi.
- The IP `192.168.1.29` used in `discovery_socket.connect()` is your server's IP.

📌 *You can find your local IP using `ipconfig` (Windows) or `ifconfig`/`ip a` (Linux/macOS).*



