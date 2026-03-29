# Real Time Chat Application

> A full-stack real-time chat web application with live message broadcasting across multiple users — built with Spring Boot WebSocket and the STOMP protocol.

![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![WebSocket](https://img.shields.io/badge/WebSocket-010101?style=flat-square&logo=socketdotio&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=flat-square&logo=bootstrap&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-22c55e?style=flat-square)

---

## Why I Built This

I wanted to understand what actually powers real-time features — the kind you see in Slack, WhatsApp Web, or any live collaboration tool. HTTP request-response cycles can't do this. WebSockets can. Building this taught me how persistent two-way connections work, how a message broker routes events between clients, and what a production-style backend architecture looks like in Spring Boot.

---

## Features

- 💬 Real-time message broadcasting — messages appear instantly for all connected users
- 👥 Multi-user support — multiple browser sessions connected simultaneously
- 🎨 Clean, responsive UI built with Bootstrap
- 🔌 Persistent WebSocket connections managed server-side via Spring Boot
- 📡 STOMP protocol for structured, topic-based message routing

---

## Demo

**Flow: User sends a message**
```
Browser (Client A)
  └── Sends via WebSocket → STOMP broker (Spring Boot)
                                └── Broadcasts to all subscribers
                                        ├── Client A (sees own message)
                                        ├── Client B (receives instantly)
                                        └── Client C (receives instantly)
```

Open two browser tabs → type in one → message appears in both instantly.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Backend | Spring Boot, WebSocket, STOMP |
| Frontend | HTML, CSS, JavaScript, Bootstrap |
| Protocol | WebSocket (RFC 6455), STOMP over WebSocket |
| Build Tool | Maven |

---

## How to Run

**Prerequisites:** Java 17+, Maven

```bash
# Clone the repository
git clone https://github.com/YOUR_GITHUB_USERNAME/realtime-chat-app.git
cd realtime-chat-app

# Build and run
mvn spring-boot:run

# Open in browser
http://localhost:8080
```

Open in two browser tabs to simulate multiple users chatting in real time.

---

## Project Structure

```
realtime-chat-app/
├── src/
│   └── main/
│       ├── java/
│       │   └── com/chat/
│       │       ├── config/         # WebSocket + STOMP configuration
│       │       ├── controller/     # Message handling endpoints
│       │       └── model/          # Message data model
│       └── resources/
│           └── static/
│               ├── index.html      # Chat UI
│               ├── app.js          # WebSocket client logic
│               └── style.css       # Styling
└── pom.xml
```

---

## Key Concepts Demonstrated

- **WebSocket protocol** — persistent, full-duplex communication channel between client and server
- **STOMP messaging** — structured publish/subscribe model over WebSocket
- **Spring Boot configuration** — registering message brokers and STOMP endpoints
- **Frontend WebSocket client** — connecting, subscribing to topics, and sending frames via JavaScript
- **Separation of concerns** — clean split between backend message logic and frontend rendering
