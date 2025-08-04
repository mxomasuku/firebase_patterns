# Firebase Auth Session Cookie Demo

This project demonstrates how to test Firebase Authentication using Node.js, Firebase Emulator Suite, Axios, and server-created session cookies — all without a frontend.

## Features

- Secure login using email & password (via emulator)
- Session cookie creation using Firebase Admin SDK
- Emulated Firebase Auth REST API usage via Axios
- Express + TypeScript backend
- Cookie-based session management
- Fully local and safe to test

## Stack

- Node.js + Express
- Firebase Admin SDK
- Firebase Emulator Suite
- Axios
- TypeScript
- dotenv

## Quick Clone (Only This Demo)

Want to clone just this folder from the monorepo?

```bash
git clone --filter=blob:none --no-checkout https://github.com/mxomasuku/firebase_patterns.git
cd firebase_patterns
git sparse-checkout init --cone
git sparse-checkout set firebase-auth-session-cookie-demo
git checkout main
```

## Setup Instructions

### 1. Install Dependencies

```bash
cd firebase-auth-session-cookie-demo
npm install
```

### 2. Add Firebase Admin Credentials

- Place your `firebase-adminsdk.json` credentials file in the root
- Add a `.env` file with the following content:

```env
FIREBASE_AUTH_EMULATOR_URL=http://127.0.0.1:9099
```

> Do **not** use real credentials. This is designed for Firebase Emulator only.

### 3. Start the Firebase Auth Emulator

```bash
firebase emulators:start --only auth
```

### 4. Run the Backend

```bash
npm run dev
```

The server should now be running at:  
http://localhost:3000

## API Endpoints

### POST /api/login

Accepts email and password. Returns a secure session cookie in Set-Cookie.

```json
{
  "email": "admin@example.com",
  "password": "test123"
}
```

### GET /api/protected (Coming Soon)

Will demonstrate how to use Firebase Admin to verify session cookies.

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

Created by [Mxolisi Masuku](https://github.com/mxomasuku)
