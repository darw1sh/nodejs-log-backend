# Logging Backend

Node.js + Express + Mongoose backend for the logging system. This repository contains the API server that handles developer authentication, application management, and log ingestion/retrieval.

## Quick Start

1. Copy `.env.example` to `.env` and set required values.
2. Install dependencies:

```bash
npm install
```

3. Run the server (development):

```bash
npm run dev
```

Use in-memory MongoDB for quick local testing:

```bash
USE_INMEMORY=true npm run dev
```

## Environment Variables

- `PORT` — server port (default: `3000`)
- `MONGO_URI` — MongoDB connection string
- `JWT_SECRET` — JWT signing secret
- `JWT_EXPIRES_IN` — JWT expiry (e.g. `7d`)
- `USE_INMEMORY` — if `true`, starts an in-memory MongoDB instance for testing

## API Endpoints

- `POST /api/users/register` — register a developer; returns `apiKey` and `token`
- `POST /api/users/login` — login; returns `apiKey` and `token`
- `POST /api/applications` — create an application (requires JWT)
- `GET /api/applications` — list applications for the authenticated developer
- `POST /api/applications/:name/logs` — ingest a log (requires `x-api-key` header)
- `GET /api/applications/:name/logs` — retrieve logs with pagination, sorting and optional filters

## Testing

1. Start the server with `USE_INMEMORY=true` for a clean ephemeral database.
2. Register or log in to receive an `apiKey`.
3. Create an application using the returned JWT.
4. Send logs to `POST /api/applications/:name/logs` with header `x-api-key: <API_KEY>`.

## License

MIT
