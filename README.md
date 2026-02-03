# NestChat 🐦💬

NestChat is a real-time chat application built with Next.js that enables instant messaging between authenticated users using a Redis-based pub/sub system.
A real-time chat app using Google OAuth, Redis pub/sub, and WebSockets for instant message delivery.
Users sign in with Google authentication, connect with other users, and exchange messages in real time through a modern and responsive interface.
This project was created as a personal exploration of real-time communication, authentication flows, and scalable messaging architecture using modern web technologies.

---

## Features

- Google authentication using NextAuth
- Real-time messaging with Socket.io
- Redis (Upstash) pub/sub for fast message broadcasting
- Automatic message updates across connected clients
- Responsive UI with Tailwind CSS and ShadCN UI
- Fully typed codebase with TypeScript

---

## Architecture

NestChat uses a Redis-backed pub/sub model combined with WebSockets to handle real-time messaging.

- Socket.io maintains persistent client connections
- Redis (Upstash) acts as a message broker
- Messages are published to Redis channels
- Subscribed clients receive updates instantly

This design allows the system to scale horizontally without tightly coupling clients to each other.

---

## Tech Stack

- **Framework**: Next.js
- **Language**: TypeScript
- **Styling**: Tailwind CSS, ShadCN UI
- **Authentication**: NextAuth (Google Provider)
- **Real-time**: Socket.io
- **Messaging Layer**: Redis (Upstash)

---

## How It Works

1. Users sign in using their Google account.
2. After authentication, the client establishes a WebSocket connection.
3. Messages are published to Redis channels.
4. Redis broadcasts messages to all subscribed clients.
5. Connected users receive messages instantly without page refreshes.

This architecture keeps message delivery fast, scalable, and decoupled from the UI layer.

---

## Getting Started

### Prerequisites

- Node.js (v18 or newer recommended)
- Upstash Redis account
- Google OAuth credentials

---

### Installation

```bash
git clone https://github.com/your-username/nestchat.git
cd nestchat
npm install
```


### Environment Variables

```env
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=your-secret

GOOGLE_CLIENT_ID=your-google-client-id
GOOGLE_CLIENT_SECRET=your-google-client-secret

UPSTASH_REDIS_REST_URL=your-redis-url
UPSTASH_REDIS_REST_TOKEN=your-redis-token
```
### Run the App
```bash
npm run dev
```

---

## Project Status

This project is currently not fully functional due to changes in Upstash Redis channel and pub/sub behavior.
To restore real-time messaging, the Redis pub/sub implementation needs to be updated to align with the latest Upstash Redis API and channel configuration.
Despite this, the overall architecture, authentication flow, and real-time design remain valid and intentionally documented.

