# Real-Time Chat App

A real-time chat application built with **Node.js**, **Express**, and **Socket.IO**, featuring message persistence, reliable delivery guarantees, and horizontal scaling.

## Features

- 💬 **Real-time messaging** using WebSockets (Socket.IO)
- 💾 **Message persistence** with SQLite — chat history survives server restarts
- 🔄 **Connection state recovery** — automatically restores missed messages after a brief disconnection (e.g. switching from Wi-Fi to mobile data)
- ✅ **Exactly-once delivery guarantee** — messages are never lost or duplicated, even under unreliable network conditions, using unique client offsets and retry logic
- ⚡ **Horizontal scaling** — uses Node.js `cluster` module to run one Socket.IO server per CPU core, with the Cluster Adapter forwarding events between them
- 🧹 Clear chat functionality

## Tech Stack

- **Backend:** Node.js, Express, Socket.IO
- **Database:** SQLite
- **Scaling:** Node.js Cluster module + `@socket.io/cluster-adapter`

## Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) installed

### Installation

```bash
git clone https://github.com/Jayant202003/socket-chat-example.git
cd socket-chat-example
npm install
```

### Running locally

```bash
node index.js
```

The app will spin up one server per available CPU core (e.g. `http://localhost:3000`, `http://localhost:3001`, etc.). Open any of these ports in your browser to start chatting.

## Live Demo

🔗 [Live demo link here]

## What I Learned

This project was built to explore real-world challenges in building real-time applications:
- Handling unreliable network connections gracefully
- Guaranteeing message delivery without duplication
- Scaling a stateful, real-time system across multiple processes

## License

MIT