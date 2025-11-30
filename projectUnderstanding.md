# 📹 Zoom Clone – MERN Stack + WebRTC + Socket.io

A Real-Time Video Conferencing Application

This project is a **Zoom-like video meeting platform** built using the **MERN stack** with **WebRTC** for real-time media streaming and **Socket.io** for peer-to-peer signaling and communication.

The application supports **video calls, chat, authentication using tokens, meeting joining using unique tokens, and P2P communication**.

---

## ⭐ Key Features

* 🔐 **Token-based Authentication** (stateless + secure)
* 🎥 **Peer-to-Peer Video Calling** using **WebRTC**
* 🔊 Real-time communication using **Socket.io**
* 💬 In-call chat system
* 🧩 Modular backend structure (Express, sockets, controllers)
* 🎨 Frontend UI using **React + Material UI**
* 🗄️ Database management using **MongoDB + Mongoose**
* 🚀 Secure password handling using **bcrypt & crypto**
* 🌍 CORS handled properly for cross-origin requests

---

# 🧠 Understanding WebRTC 

**WebRTC (Web Real-Time Communication)** is a browser technology that allows **real-time video, audio, and data sharing directly between two devices**.

👉 In simple words:
**WebRTC allows two people to communicate directly without sending video/audio through a server.**

This is called **Peer-to-Peer (P2P)** connection.

* Server is only used for **signaling** (exchanging connection info)
* Video & audio stream flows **directly between users**

This makes video calls:

* Faster
* Low-latency
* More private
* Less server cost

---

# 🛠 Tech Stack

### **Frontend**

* React.js
* Material UI
* Axios
* WebRTC
* CSS

### **Backend**

* Node.js
* Express.js
* MongoDB + Mongoose
* bcrypt (password hashing)
* crypto (secure token generation)
* Socket.io (real-time communication)
* HTTP Status Codes
* CORS middleware

### **Database**

* MongoDB (IP whitelist used: `0.0.0.0/0` during development for open access)

---

# 🔐 Authentication – Token-Based Flow 

A **token** is a small piece of data that represents the user.
Token = “Digital ID Card”

It helps verify:

* Who is making the request
* Whether they are allowed to access the resource

### **Types of Tokens**

* Access Token
* Refresh Token
* ID Token

### 🔄 **Authentication Flow**

**Step 1:** User enters username & password
**Step 2:** Server checks credentials
**Step 3:** Server generates a **token**
**Step 4:** Token is saved on client (localStorage or cookies)
**Step 5:** For every protected request → client sends token in **Authorization header**
**Step 6:** Server verifies token → allows or denies access

Token is stored instead of sensitive data because:

* Storing password or private info in localStorage = insecure
* Token is safer & can be invalidated via cron job

### Why use `crypto.randomBytes()`?

To generate a **secure, unpredictable token**, making it extremely difficult for attackers to guess.

---

# 🌐 Understanding CORS (Cross-Origin Resource Sharing)

CORS is a browser security mechanism that controls **which websites can access resources from another website**.

Without CORS → Browser blocks cross-domain requests.

Example:
Frontend: `delta.com`
Backend API: `zoom.delta.com`
These are **different origins**, so browser blocks request.

Server must allow it using:

```
Access-Control-Allow-Origin: delta.com
```

### Important CORS Headers

* **Access-Control-Allow-Origin** – which domains can access
* **Access-Control-Allow-Methods** – GET, POST, PUT...
* **Access-Control-Allow-Headers** – what headers are allowed
* **Access-Control-Allow-Credentials** – cookies allowed or not
* **Access-Control-Expose-Headers** – what headers browser can read

---

# 🧩 Backend Architecture

### 📁 Folder Structure (backend)

```
backend/
│-- src/
│   ├── controllers/
│   ├── socketManager.js
│   ├── models/
│   ├── routes/
│   ├── server.js
│-- package.json
```

### 🔧 Setup Steps

```
cd backend
npm init
npm install express mongoose cors bcrypt crypto nodemon http-status
```

Add in `package.json`:

```
"type": "module"
```

### 🌐 MongoDB IP Whitelist

Use `0.0.0.0/0` ONLY during development → allows connection from any IP.
Not safe for production.

---

# 🔌 Socket.io – Real-Time Signaling

WebRTC requires a signaling mechanism. Here we use **Socket.io**.

### Why create a custom server?

```
const server = createServer(app);
const io = new Server(server);
```

* Express handles API routes
* A separate socket server manages real-time events
* Both are attached to the same HTTP server

### 📡 Socket Events Used

* `connection`
* `join-call`
* `signal`
* `chatMessage`
* `disconnect`

### How it works:

* When user joins meeting → socket generates **Socket ID**
* Meeting path = key
* Socket ID = value

For example:

```
/meeting/123 → socketId: "sx5G8H9"
```

### Chat Message Flow

Backend:

```
io.emit("chatMessages", data)
```

Frontend:

```
socket.on("chatMessages", ()=>{...})
```

Logic ensures:

* Sender and receiver usernames match
* Users don’t message themselves in call

---

# 🎥 Frontend – React + WebRTC Integration

### Steps:

1. Install router

   ```
   npm i react-router-dom
   ```
2. Create pages → Home, Join Meeting, Meeting Room
3. Use Material UI for UI components
4. WebRTC handles media stream:

   ```
   navigator.mediaDevices.getUserMedia()
   ```
5. Socket.io manages signaling
6. VideoMeeting.jsx handles:

   * Creating peer connection
   * Displaying remote videos
   * Updating chat messages

---

# 🚀 Meeting Join Logic (Token Based)

To join a meeting:

* User does NOT enter username/password
* They only enter **meeting token**

Backend receives token → fetches associated user data → joins meeting.

---

# 📌 Additional Security Feature: Token Invalidation

Cron jobs can invalidate tokens:

* After timeout
* After logout
* When meeting ends

---

# 📄 Conclusion

This Zoom Clone project demonstrates strong understanding of:

* Real-time communication
* WebRTC peer-to-peer architecture
* Socket.io event-driven programming
* Secure MERN stack development
* Authentication using tokens
* CORS and backend networking
* React component structure
* Database management with MongoDB

It is a full end-to-end real-time system built using modern web technologies.

---

