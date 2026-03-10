# Copilot Coding Agent Incident Lab

This lab simulates a production incident in a shipping quote service.

## Setup

```bash
npm install
npm test
npm start
```

Open:
- `GET /health`
- `GET /api/quote?zip=33139`

## Seeded bug

The retry logic in `src/retry.js` is intentionally flawed:
- it retries too aggressively
- it ignores `Retry-After`
- it retries some requests that should not be retried
