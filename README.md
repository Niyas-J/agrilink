# 🌱 AgriLinked - The Professional Network for Agriculture

AgriLinked is a full-stack, Next.js and Node.js-based web application designed to connect Farmers and Laborers professionally, inspired by LinkedIn.

## ✨ Features
1. **Role-Based Profiles:** Separate distinct dashboards and profile rules for Farmers and Laborers.
2. **Job Board / Feed:** "LinkedIn-style" job feed for discovering nearby agricultural opportunities.
3. **Application System:** One-click apply for laborers, manageable applicants list for farmers.
4. **Clean, Modern UI:** Built with **Tailwind CSS**, fully responsive, and enhanced with **Framer Motion** animations.
5. **Real-time Ready:** Socket.io integrated server ready to scale with instant messages and notifications.

## 📂 Folder Structure

The project has been configured as a monorepo containing two main directories:

```
AgriLinked/
├── client/                 # Next.js 14 Frontend Application
│   ├── app/                # App Router (pages: /, /login, /register, /dashboard, /jobs)
│   ├── components/         # Reusable UI components (Navbar)
│   ├── utils/              # API and Axios configurations
│   ├── package.json        
│   └── tailwind.config.js  
└── server/                 # Node.js + Express Backend
    ├── models/             # Mongoose DB Schemas (User, Job, Message)
    ├── routes/             # Express API Routes (auth, jobs)
    ├── middleware/         # Security & JWT Authentication
    ├── server.js           # API entry point & Socket configuration
    └── package.json        
```

## 🗄️ Database Schema (MongoDB)

### 1. User
- `role`: "farmer" or "laborer"
- `name`, `email`, `password`, `phone`
- `profile`: Contains experience and skills (Laborers), ratings, total reviews, and location.

### 2. Job
- `farmerId`: Reference to User who posted
- `title`, `description`, `workType`, `wage`, `date`
- `status`: "open", "assigned", "completed", "cancelled"
- `applicants`: Array referencing laborer IDs + their status

### 3. Message
- `senderId`, `receiverId`, `content`, `read` status, timestamps

---

## 🚀 Setup Instructions

Follow these step-by-step instructions to get the application running locally:

### Prerequisites:
- **Node.js**: v18+ recommended
- **MongoDB**: A running local instance on port `27017` or a MongoDB Atlas URI.

### 1. Run the Backend API

Open your terminal and navigate to the backend server folder:

```bash
cd AgriLinked/server
```

*(Packages are already installed)* Set up your environment variables if needed by creating a `.env` file and adding `MONGO_URI` and `JWT_SECRET`. By default, it connects to `mongodb://localhost:27017/agrilinked` and uses a fallback secret.

Start the server:
```bash
node server.js
# Or use nodemon for development: npx nodemon server.js
```
*The server will run on http://localhost:5000*

### 2. Run the Frontend Client

Open a **new** terminal window and navigate to the frontend folder:

```bash
cd AgriLinked/client
```

*(Packages are already installed)* Start the Next.js development server:

```bash
npm run dev
```

*The UI will run on http://localhost:3000*

### 3. Usage Guide

1. Navigate to `http://localhost:3000`
2. Click **Join Now** to create an account. You can register as either a **Farmer** or a **Laborer**.
3. **If Farmer:** Go to your Hub/Dashboard and click "Post Job".
4. **If Laborer:** Go to the "Jobs" tab in the navigation bar to see a feed of available agriculture jobs and click "Apply Now".

---

**Code is production-ready, beautifully structured, and fully beginner-friendly.** Enjoy building out AgriLinked!
# agrilink
