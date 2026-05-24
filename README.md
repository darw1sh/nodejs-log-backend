# AI Logging Backend

Node.js + Express + Mongoose backend for the logging system.

## Quick Start

1. Copy `.env.example` to `.env` and set the values.
2. Install dependencies:

```bash
npm install
```

3. Run the server:

```bash
npm run dev
```

## Notes

- Use `USE_INMEMORY=true` for local smoke testing without a MongoDB instance.
- The API provides developer auth, application management, and log ingestion/retrieval.
