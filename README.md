# WebSocket Chat Application

This project is a WebSocket-based chat server written in Go. The server pairs clients for chat sessions, allows clients to send messages to their partners, and handles client disconnections and waiting clients. It uses the Gorilla WebSocket package for WebSocket connections.

## Features
- Client Pairing: Automatically pairs clients for one-on-one chat sessions.
- Message Handling: Forwards messages between paired clients.
- Waiting List: Maintains a list of clients waiting for a partner.
- Client Management: Displays current client count and their statuses.
- Disconnect Handling: Manages client disconnections and updates partner statuses.

## Getting Started

### Prerequisites
Make sure you have Go installed on your machine. You can download and install Go from the official Go website.

### Installing

1. Clone the repository:
    ```sh
    git clone https://github.com/hoangnguyen2809/Chitchat.git
    ```

2. Install Go dependencies:
    ```sh
    go get github.com/gorilla/websocket
    ```

3. Run the server:
    ```sh
    go run main.go server.go
    ```

4. Open `http://localhost:8080/` in your browser to start the chat application.

### Demo

![GIF](./demo.gif)

### Overview
- Client Struct: Represents a connected client, including the name, WebSocket connection, partner client, and a channel for sending messages.
- Server Struct: Manages client connections, pairing clients, and broadcasting messages.
- HandleConnection Function: Handles new client connections, manages chat sessions, and updates client states.
- pairClient Function: Pairs a client with another waiting client or puts them on the waiting list.
- pairWaitingClients Function: Pairs up clients from the waiting list as necessary.
- broadcastClientCount Function: Sends the current client count to all connected clients.
