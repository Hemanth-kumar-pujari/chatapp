# ChatApp

A real-time, one-to-one chat application built with React, Express, MongoDB, and Socket.IO. Create an account, find a conversation, and exchange messages in a responsive chat interface.

[Features](#features) · [Quick start](#quick-start) · [How to use](#how-to-use) · [Project structure](#project-structure) · [Scripts](#scripts)

## Features

- **Account access:** sign up, log in, and log out.
- **Find a conversation:** search available conversations by a user's name.
- **Live messaging:** send and receive messages using Socket.IO; conversations and messages are stored in MongoDB.
- **Online status updates:** the server broadcasts connected users when sockets connect or disconnect.
- **Chat UI:** conversation list, message timestamps, profile avatars, and send/loading feedback.

## Quick start

### Requirements

- Node.js and npm
- A MongoDB database and connection URI

### 1. Configure environment variables

Create a `.env` file in the repository root:

```env
MONGO_URI=your_mongodb_connection_uri
JWT_SECRET=replace_with_a_long_random_secret
PORT=5000
```

`PORT` is optional; the backend defaults to `5000`.

### 2. Install dependencies

```bash
npm install
npm install --prefix frontend
```

### 3. Start the app

Open two terminals from the repository root.

**Terminal 1 — backend:**

```bash
npm run server
```

**Terminal 2 — frontend:**

```bash
npm run dev --prefix frontend
```

Open [http://localhost:3000](http://localhost:3000). The Vite development server proxies `/api` requests to the backend at `http://localhost:5000`.

## How to use

1. **Create an account** from the sign-up screen, or log in with an existing account.
2. **Choose a conversation** from the sidebar, or use the search field to find a listed user by name (search requires at least three characters).
3. **Send a message** using the message box. New messages appear in the conversation, and a connected recipient can receive them in real time.
4. **Log out** with the sidebar logout control when finished.

## Interactive guide

<details>
<summary>What happens when I send a message?</summary>

The frontend submits the message to the Express API. The backend saves it in MongoDB and, when the recipient is connected, emits a `newMessage` Socket.IO event to that recipient.

</details>

<details>
<summary>How do I build the production frontend?</summary>

Run the root build script:

```bash
npm run build
```

This installs the frontend dependencies and builds the Vite app into `frontend/dist`. The Express server is configured to serve that build.

</details>

<details>
<summary>Where can I report a bug or suggest an improvement?</summary>

[Open an issue](https://github.com/Hemanth-kumar-pujari/chatapp/issues) and include steps to reproduce the problem or a clear description of the suggestion.

</details>

## Scripts

| Command | Description |
| --- | --- |
| `npm run server` | Start the backend with nodemon. |
| `npm start` | Start the backend with Node.js. |
| `npm run build` | Install frontend dependencies and build the frontend. |
| `npm run dev --prefix frontend` | Start the Vite development server. |
| `npm run build --prefix frontend` | Build the frontend only. |
| `npm run lint --prefix frontend` | Run ESLint on the frontend. |

## Project structure

```text
.
├── backend/
│   ├── controllers/   # Authentication, user, and message handlers
│   ├── db/            # MongoDB connection
│   ├── middlewares/   # Request middleware
│   ├── model/         # Mongoose models
│   ├── routes/        # API routes
│   ├── socket/        # Socket.IO server
│   └── server.js      # Express application entry point
└── frontend/
    └── src/           # React app, pages, components, hooks, and state
```

## Tech stack

- **Frontend:** React, Vite, Tailwind CSS, DaisyUI, Zustand, Socket.IO Client
- **Backend:** Node.js, Express, Socket.IO
- **Database:** MongoDB with Mongoose
- **Authentication:** JSON Web Tokens and bcryptjs

---

<div align="center">Built for conversations that feel immediate. 💬</div>
