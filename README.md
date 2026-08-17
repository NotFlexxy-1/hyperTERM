# HyperTERM

**HyperTERM by hyperNET** is a real web-based SSH terminal manager designed to bring a modern Termius/PuTTY-style experience to the browser.

> **Status:** Active development

## Short Description

> A real browser-based SSH client with saved terminals, xterm.js, WebSockets, PTY support, authentication, and encrypted SSH credentials.

## Features

- Real SSH connections
- Interactive PTY terminal
- xterm.js browser terminal
- WebSocket terminal streaming
- Saved SSH terminals
- Password and SSH private-key authentication
- SQLite-backed terminal management
- User authentication
- Google OAuth support
- Encrypted SSH credentials at rest
- Terminal resize support
- Reconnect support
- Responsive dark interface
- hyperNET branding

## Architecture

```text
Browser
   │
   │ HTTPS / WebSocket
   ▼
HyperTERM Backend
   │
   ├── Authentication
   ├── SQLite
   ├── Credential Encryption
   ├── SSH Manager
   ├── PTY
   └── WebSocket Bridge
   │
   ▼
Real SSH Server / VPS
```

## Technology

### Frontend

- HTML
- CSS
- Vanilla JavaScript
- xterm.js
- xterm-addon-fit

### Backend

- Python
- FastAPI
- Uvicorn
- AsyncSSH / SSH backend
- WebSockets
- SQLite
- Argon2 / secure password hashing
- Cryptography

## Branding

HyperTERM uses the official hyperNET logo:

https://i.postimg.cc/VvWF53xk/hypernet-logo.png

HyperTERM is a hyperNET product.

## Important Security Notes

HyperTERM is designed to keep SSH credentials on the backend rather than exposing saved credentials to the browser.

Never commit:

- `.env`
- production secrets
- encryption keys
- SSH private keys
- passwords
- database files containing production credentials

Use strong, unique values for all production secrets.

## Deployment

The project can be packaged and deployed as a Dockerized Python service.

Typical startup:

```bash
uvicorn backend.main:app --host 0.0.0.0 --port ${PORT:-8000}
```

See the project deployment files and backend documentation for the exact environment configuration.

## Environment Variables

Typical configuration includes:

```text
HYPERTERM_SECRET_KEY=
HYPERTERM_ENCRYPTION_KEY=
DATABASE_PATH=
GOOGLE_CLIENT_ID=
GOOGLE_CLIENT_SECRET=
GOOGLE_REDIRECT_URI=
```

Never publish real values.

## Project Policy

HyperTERM is proprietary software.

The repository may be publicly visible on GitHub, but public visibility does **not** grant permission to copy, modify, redistribute, rebrand, resell, sublicense, or commercially exploit the software.

See `LICENSE` for the complete terms.

## Trademark / Branding

**HyperTERM** and **hyperNET** are project/brand names. Do not use the project's branding, logos, or product identity to represent an unofficial fork or derivative service.

## Contributions

Contributions are not automatically permitted.

Any contribution, patch, pull request, or code submission may be accepted only at the sole discretion of the copyright owner and subject to the project's licensing terms.

## Disclaimer

HyperTERM is provided for legitimate system administration and authorized infrastructure management.

You are responsible for ensuring that you have permission to access and manage every server to which you connect.

## Copyright

Copyright © 2026 hyperNET. All rights reserved.
