<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:2563EB,100:7C3AED&height=200&section=header&text=ChatApp&fontSize=64&fontColor=ffffff&animation=fadeIn&fontAlignY=38" alt="ChatApp — real-time conversations" width="100%" />

  <h3>Good conversations happen in real time.</h3>
  <p>A modern one-to-one chat app built with React, Express, MongoDB, and Socket.IO.</p>

  <p>
    <a href="#features">✨ Explore features</a> ·
    <a href="#quick-start">🚀 Get started</a> ·
    <a href="#how-to-use">💬 How to use</a> ·
    <a href="#project-structure">📁 Project structure</a>
  </p>

  <p>
    <img src="https://img.shields.io/badge/React-frontend-61DAFB?logo=react&logoColor=white" alt="React frontend" />
    <img src="https://img.shields.io/badge/Node.js-backend-339933?logo=nodedotjs&logoColor=white" alt="Node.js backend" />
    <img src="https://img.shields.io/badge/MongoDB-database-47A248?logo=mongodb&logoColor=white" alt="MongoDB database" />
    <img src="https://img.shields.io/badge/Socket.IO-real--time-010101?logo=socketdotio&logoColor=white" alt="Socket.IO real-time messaging" />
  </p>
</div>

---

## ✨ Features

| | Feature | What it does |
| --- | --- | --- |
| 🔐 | **Account access** | Sign up, log in, and log out securely. |
| 🔎 | **Find a conversation** | Search available conversations by a user's name. |
| ⚡ | **Live messaging** | Send and receive messages with Socket.IO; conversations and messages are stored in MongoDB. |
| 🟢 | **Online status** | The server broadcasts connected users when sockets connect or disconnect. |
| 🎨 | **Responsive chat UI** | Browse conversations, view timestamps and profile avatars, and get send/loading feedback. |

## 🚀 Quick start

### Prerequisites

- [Node.js](https://nodejs.org/) and npm
- A MongoDB database and connection URI

### 1. Configure environment variables

Create a `.env` file in the repository root:

```env
MONGO_URI=your_mongodb_connection_uri
JWT_SECRET=replace_with_a_long_random_secret
PORT=5000
```

> `PORT` is optional; the backend defaults to `5000`.

### 2. Install dependencies

```bash
npm install
npm install --prefix frontend
```

### 3. Start the app

Open two terminals from the repository root.

**Terminal 1 — backend**

```bash
npm run server
```

**Terminal 2 — frontend**

```bash
npm run dev --prefix frontend
```

Open [http://localhost:3000](http://localhost:3000). The Vite development server proxies `/api` requests to the backend at `http://localhost:5000`.

## 💬 How to use

1. **Create an account** from the sign-up screen, or log in with an existing account.
2. **Choose a conversation** from the sidebar, or search for a listed user by name. Search requires at least three characters.
3. **Send a message** using the message box. A connected recipient can receive it in real time.
4. **Log out** with the sidebar logout control when you're finished.

## 🧭 Interactive guide

<details>
<summary>⚡ What happens when I send a message?</summary>

The frontend submits the message to the Express API. The backend saves it in MongoDB and, when the recipient is connected, emits a `newMessage` Socket.IO event to that recipient.

</details>

<details>
<summary>📦 How do I build the production frontend?</summary>

Run the root build script:

```bash
npm run build
```

This installs the frontend dependencies and builds the Vite app into `frontend/dist`. The Express server is configured to serve that build.

</details>

<details>
<summary>🛠️ Where can I report a bug or suggest an improvement?</summary>

<a href="https://github.com/Hemanth-kumar-pujari/chatapp/issues">Open an issue</a> and include steps to reproduce the problem or a clear description of your suggestion.

</details>

## 🧰 Scripts

| Command | Description |
| --- | --- |
| `npm run server` | Start the backend with nodemon. |
| `npm start` | Start the backend with Node.js. |
| `npm run build` | Install frontend dependencies and build the frontend. |
| `npm run dev --prefix frontend` | Start the Vite development server. |
| `npm run build --prefix frontend` | Build the frontend only. |
| `npm run lint --prefix frontend` | Run ESLint on the frontend. |

## 📁 Project structure

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

## 🧩 Tech stack

- **Frontend:** React, Vite, Tailwind CSS, DaisyUI, Zustand, Socket.IO Client
- **Backend:** Node.js, Express, Socket.IO
- **Database:** MongoDB with Mongoose
- **Authentication:** JSON Web Tokens and bcryptjs

---

<div align="center">
  <strong>Made for conversations that feel immediate. 💬</strong>
  <br />
  <a href="#top">⬆️ Back to top</a>
</div>
