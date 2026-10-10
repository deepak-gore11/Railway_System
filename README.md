# Railway Ticket Booking System - Group 3 Authentication Module

This project is a beginner-friendly starter implementation for the Group 3 authentication and user management module of a railway booking system.

## Overview

The application includes:

- user registration
- login with secure password validation
- logout and cookie-based session handling
- password reset flow with OTP verification
- secure profile management
- protected dashboard and access control
- SQLite-backed user storage
- responsive railway-themed frontend

## Technology stack

- Frontend: React + Vite
- Backend: Node.js + Express.js
- Database: SQLite (SQL-based, beginner-friendly, and compatible with the project requirement to use a SQL engine)
- Auth: bcryptjs and JWT
- Security: HttpOnly cookies, password hashing, input validation, rate limiting

## Project structure

- `client/` — React frontend
- `server/` — Express backend and SQLite database logic
- `.env.example` — environment variable template
- `README.md` — start-up and testing instructions

## Required software

- Node.js 18+
- npm 9+

## Installation

1. Open a terminal in the project root.
2. Install the root dev tools:

```bash
npm install
```

3. Install frontend dependencies:

```bash
cd client && npm install
```

4. Install backend dependencies:

```bash
cd server && npm install
```

## Environment configuration

1. Copy the example environment file:

```powershell
Copy-Item .env.example .env
```

Or in bash:

```bash
cp .env.example .env
```

2. Update the values if needed.

Example values:

```env
PORT=5000
NODE_ENV=development
JWT_SECRET=replace_with_secure_secret
CLIENT_URL=http://localhost:5173
```

## Start the app

Start the backend:

```bash
cd server && npm run dev
```

Start the frontend:

```bash
cd client && npm run dev -- --host 0.0.0.0
```

Or start both at once from the project root:

```bash
npm run dev
```

## Testing

Backend tests:

```bash
cd server && npm test
```

Frontend build check:

```bash
cd client && npm run build
```

## Important notes

- This is a student-friendly starter module and intentionally does not implement booking payments or ticket generation.
- OTPs are logged to the backend console in development mode for learning purposes only.
- In production, use a real email provider and do not log OTPs or reset secrets.
- Secret configuration must not be hardcoded in source files.

## Authentication flow

1. User registers with name, email, phone, and password.
2. Password is hashed before storage.
3. User logs in with email and password.
4. JWT is created and stored in an HttpOnly cookie.
5. Protected pages and API routes validate the session.
6. Forgot password flow generates an OTP and verifies it before password reset.

## Known limitations

- Real email delivery is not configured by default.
- Booking, ticket, and payment logic belong to other project groups.
- SQLite is used for easy local setup; a production deployment should use the approved SQL engine and environment configuration of the team.
