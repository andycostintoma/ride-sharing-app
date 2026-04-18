## Web Frontend

This folder contains the frontend client for the ride-sharing system.

It is a Next.js application that sits alongside the Go services and supports the overall distributed-system workflow rather than acting as a standalone toy frontend.

### Run locally

```bash
npm run dev
```

Then open `http://localhost:3000`.

### Role in the system

- user-facing frontend for the ride-sharing flows
- companion client for the backend services and gateway
- part of the overall local distributed setup driven by the root project tooling
