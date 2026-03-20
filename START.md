# SAJIS App — How to Run

## Prerequisites
You need these installed on your computer:
- Node.js v18+ → https://nodejs.org
- MongoDB Community → https://www.mongodb.com/try/download/community

---

## Step 1: Start MongoDB

**macOS (Homebrew):**
```
brew services start mongodb-community
```

**Ubuntu/Linux:**
```
sudo systemctl start mongod
```

**Windows:**
```
net start MongoDB
```

**Verify MongoDB is running:**
```
mongosh --eval "db.runCommand({ping:1})"
```
You must see: `{ ok: 1 }`

---

## Step 2: Start the Backend (Terminal 1)

```
cd server
npm install
node seedAdmin.js
npm run dev
```

Wait for BOTH these lines:
```
✅ MongoDB connected: 127.0.0.1
🚀 SAJIS Server running on http://localhost:5000
```

**Test it works:** Open http://localhost:5000 in your browser.
You should see: `{"message":"SAJIS API is running ✅"}`

---

## Step 3: Start the Frontend (Terminal 2)

Open a NEW terminal window:
```
cd client
npm install
npm start
```

The app opens at http://localhost:3000

---

## Login Credentials

**Admin:**
- Email: admin@sajis.lk
- Password: admin123
- Go to /login → select "Admin Login"

**User:**
- Register a new account at /register

---

## Troubleshooting

| Error | Fix |
|-------|-----|
| "Failed to fetch" | Backend is not running. Do Step 2 first. |
| "MongoDB connection failed" | MongoDB is not running. Do Step 1 first. |
| Port 5000 in use | Run: `lsof -i :5000` then `kill -9 <PID>` |
| npm install fails | Delete node_modules and try again |
