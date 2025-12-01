# 🎥 Zoom Clone – Real-Time Video Conferencing Platform

![Status](https://img.shields.io/badge/Project_Status-Completed-brightgreen)

![TechStack](https://img.shields.io/badge/Tech_Stack-MERN%20%7C%20WebRTC%20%7C%20Socket.io-blue)

![RealTime](https://img.shields.io/badge/Real_Time-Video%20Calling%20%7C%20Signaling-yellow)

A highly scalable and real-time **video conferencing application** inspired by Zoom, built using **WebRTC**, **Socket.io**, **React**, and **Node.js**.
This platform enables users to create meeting rooms, join video calls, exchange audio/video streams, and communicate in real time with low latency.

---

## ⭐ Why This Project?

In today’s remote-first world, real-time communication platforms like Zoom and Google Meet have become essential. This project demonstrates your ability to build:

* Real-time communication systems
* Peer-to-peer network connections
* Scalable MERN applications
* Socket.io signalling architecture
* Modern frontend UI with Material UI


---

# 📌 Table of Contents

* Overview
* Key Features
* Real-World Use Cases
* Tech Stack
* System Architecture
* Project Structure
* Installation & Setup
* Environment Variables
* How Real-Time Communication Works
* Future Scope
* Screenshots
* Demo Video
* Author

---

# 🚀 Overview

This Zoom Clone is a **production-grade real-time meeting system** where users can:

* Create or join unique meeting rooms
* Connect through peer-to-peer WebRTC
* Share video/screen, audio, mute/unmute
* Handle participant join/leave events
* Communicate using secure signalling channels

The system uses **Socket.io** for signalling & real-time events, while WebRTC establishes direct media transmission between participants for low-latency streaming.

---

# 🎯 Key Features

### 👥 Meeting Rooms
- Create a unique meeting ID  
- Join meetings using Room ID  
- Dynamic user join/leave notifications  

### 🎥 Video & Audio Streaming
- WebRTC PeerConnection  
- Toggle camera / microphone  
- Multi-user video grid  

### 🖥️ Screen Sharing
- Share full screen, window, or browser tab  
- Smooth WebRTC-based screen stream  
- Auto-switch between camera and screen modes  

### 💬 Real-Time Chat Messaging
- Send text messages during meetings  
- Instant message delivery using Socket.io  
- Shows sender name + timestamp  

### 🔌 Real-Time Events (Socket.io)
- Broadcasting new participants  
- ICE candidate exchange  
- Offer/Answer handling  
- Room state management  

### 🔐 User Authentication
- User registration/login  
- MongoDB user storage  
- JWT-based auth (optional)  

### 🌐 Frontend UI
- Simple and modern interface  
- Material UI components  
- Responsive design  
###


# 💼 Real-World Use Cases

This Zoom Clone can be used for:

### ✔ Online Classes

Teachers can create rooms and students can join for real-time learning.

### ✔ Corporate Meetings

Team members can connect instantly without third-party tools.

### ✔ One-to-One Personal Video Calls

Friends or family can talk privately via secure P2P connections.

### ✔ Interviews & Recruitment

Companies can integrate this into hiring platforms.

### ✔ Healthcare & Online Consultation

Doctors and patients can connect through private sessions.

### ✔ Remote Collaboration

Developers, designers, and remote teams can work together instantly.

---

# 🛠 Tech Stack

### **Frontend**

* React.js
* Material UI
* Axios
* WebRTC
* Socket.io-client (Real-time event handling)
* React Router

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

* MongoDB Atlas

### **Real-Time Core**

* WebRTC (peer-to-peer)
* STUN/TURN servers (optional for NAT traversal)

---



### 🔍 How it works:

* WebRTC handles **media streaming**
* Socket.io handles **negotiation + signalling**
* MongoDB manages **users & sessions**
* React handles **UI rendering**

---

# 📁 Project Structure

```
Zoom/
│
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── models/
│   │   ├── routes/
│   │   └── app.js
│   ├── package.json
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── contexts/
│   │   ├── pages/
│   │   ├── styles/
│   │   ├── utils/
│   │   ├── App.js
│   │   └── index.js
│   ├── package.json
│
└── README.md
```

---

# ⚙️ Installation & Setup

## 🖥 Backend Setup

1️⃣ Navigate to backend

```bash
cd backend
```

2️⃣ Install required packages

```bash
npm install
```

3️⃣ Create `.env`

```
PORT=8000
MONGO_URL=your_mongo_atlas_url
```

4️⃣ Run backend

```bash
npm run dev
```
Backend API → http://localhost:8000

---

## 🌐 Frontend Setup

1️⃣ Navigate to frontend

```bash
cd frontend
```

2️⃣ Install dependencies

```bash
npm install
```

3️⃣ Run frontend

```bash
npm start
```
Frontend → http://localhost:3000

---

# 🔐 Environment Variables

### Backend `.env`

```
PORT=8000
MONGO_URL=your_mongo_connection_string
JWT_SECRET=your_secret_key
```

### Frontend `.env`

```
REACT_APP_BACKEND_URL=http://localhost:8000
```

---

# 📸 Screenshots

![Dashboard Page](https://github.com/Gayatrip-26/Zoom/blob/a4429b8e0f380f8bb7f48ea2b76bc29050235596/dashboard.png)
<p align="center"><em> Main Dashboard Page of Gayatri - VedioChat.</em></p>

![signUp1](https://github.com/Gayatrip-26/Zoom/blob/a4429b8e0f380f8bb7f48ea2b76bc29050235596/hostSignUp.png)
![signUp2](https://github.com/Gayatrip-26/Zoom/blob/a4429b8e0f380f8bb7f48ea2b76bc29050235596/UserSignUp.png)
<p align="center"><em>Sign Up Pages for Host and User to create their accounts.</em></p>

![Login](https://github.com/Gayatrip-26/Zoom/blob/a4429b8e0f380f8bb7f48ea2b76bc29050235596/Login.png)
<p align="center"><em>Login Page to access the Lobby and start/join meetings.</em></p>

![Token](https://github.com/Gayatrip-26/Zoom/blob/a4429b8e0f380f8bb7f48ea2b76bc29050235596/EnterToken.png)
<p align="center"><em>Token Entry Page for secure access to specific meeting rooms.</em></p>

![EnterLoby](https://github.com/Gayatrip-26/Zoom/blob/a4429b8e0f380f8bb7f48ea2b76bc29050235596/HostEnter.png)
![EnterLoby2](https://github.com/Gayatrip-26/Zoom/blob/a4429b8e0f380f8bb7f48ea2b76bc29050235596/UserEnter.png)
<p align="center"><em>Host and User entering their username to join the Lobby.</em></p>

![Allow](https://github.com/Gayatrip-26/Zoom/blob/a4429b8e0f380f8bb7f48ea2b76bc29050235596/AllowAccess.png)
<p align="center"><em>Permission page to allow camera and microphone access for video calls.</em></p>

![chatmessage](https://github.com/Gayatrip-26/Zoom/blob/a4429b8e0f380f8bb7f48ea2b76bc29050235596/chatMessage.png)
<p align="center"><em>Chat interface for sending messages during meetings.</em></p>

![screen](https://github.com/Gayatrip-26/Zoom/blob/a4429b8e0f380f8bb7f48ea2b76bc29050235596/screenSharing.png)
![Screen Page](https://github.com/Gayatrip-26/Zoom/blob/a4429b8e0f380f8bb7f48ea2b76bc29050235596/screenSharing1.png)
<p align="center"><em>Screen sharing feature allowing participants to share their screens during meetings.</em></p>
---

# 🔗 Understanding WebRTC + Socket.io Flow

### 1️⃣ User joins a meeting

* React sends request → backend
* Socket connects to room channel

### 2️⃣ Backend broadcasts user presence

Socket.io notifies all participants that someone joined.

### 3️⃣ WebRTC Negotiation

* Browser A sends WebRTC offer
* Browser B responds with answer
* ICE candidates exchanged

### 4️⃣ Direct video call

After negotiation, browsers connect **peer-to-peer** for real video/audio streaming.

---

# 🚀 Future Scope 

This project can be expanded into a full Zoom alternative:


### 🔹 **Recording Meetings**

Record video & audio streams using MediaRecorder API.

### 🔹 **Waiting Room**

Host admits/rejects participants.

### 🔹 **Admin Controls**

Mute/disable participant audio/video.

### 🔹 **Secure File Sharing**

Secure file sharing & document upload.

### 🔹 **AI Transcription**

Live speech-to-text using OpenAI Whisper.

### 🔹 **Grid Video Layout**

Dynamic grid like Zoom/GMeet.

### 🔹 **Turn Server Integration**

Enable more reliable calling behind strict firewalls.

---



---


# 🧑‍💻 Author

**Gayatri Patil**
Full-Stack Developer | MERN | WebRTC
GitHub: [https://github.com/Gayatrip-26](https://github.com/Gayatrip-26)
LinkedIn: https://www.linkedin.com/in/gayatri-patil-524620283/

---
