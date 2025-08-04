# Firebase Auth Session Cookie Demo

This project demonstrates how to test Firebase Authentication using Node.js, Firebase Emulator Suite, Axios, and server-created session cookies — all without a frontend.

## Features

- Secure login using email & password (via emulator)
- Session cookie creation using Firebase Admin SDK
- Emulated Firebase Auth REST API usage via Axios
- Express + TypeScript backend
- Cookie-based session management
- Fully local & safe to test

## Stack

- Node.js + Express
- Firebase Admin SDK
- Firebase Emulator Suite
- Axios
- TypeScript
- dotenv

## Setup Instructions

### 1. Clone the Repo & Install Dependencies

```bash
git clone https://github.com/yourname/firebase-auth-session-cookie-demo.git
cd firebase-auth-session-cookie-demo
npm install
```

### 2. Add Firebase Admin Credentials

- Place your `firebase-adminsdk.json` credentials file in the root
- Make sure `.env` is configured correctly:

```bash
FIREBASE_AUTH_EMULATOR_URL=http://127.0.0.1:9099
```

Note: Do NOT use real credentials for this demo. Use Firebase Emulator.

### 3. Start the Firebase Auth Emulator

```bash
firebase emulators:start --only auth
```

### 4. Run the Backend

```bash
npm run dev
```

The server should now be running on http://localhost:3000

## Endpoints

### POST /api/login

Accepts email and password. Creates a secure session cookie.

```json
{
  "email": "admin@example.com",
  "password": "test123"
}
```

### GET /api/protected (Coming Soon)

Use middleware to protect this route using session cookie verification.

## Folder Structure

```
src/
├── config/             # Firebase Admin config
├── controllers/        # Login controller
├── routes/             # Express route
├── utils/              # Axios-based auth helper
└── server.ts           # Express server entry
```

## License

MIT

---

Created by Mxolisi Masuku — https://github.com/yourname
