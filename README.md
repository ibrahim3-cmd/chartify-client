# Chartify backend

Axum API backend for the Chartify frontend.

## Local development

Install Rust, then create a local `.env` file containing the backend API credential:

```env
TOKENHARBOR_API_KEY=your-tokenharbor-api-key
```

Run the API:

```bash
cargo run
```

The server listens on `http://localhost:3001` by default. It honors the `PORT` environment variable when provided. The health endpoint is `GET /api/health`; text analysis is `POST /api/analyze`.

## Deploy to Render

Create a Blueprint from this repository and use the included `render.yaml`, or create a Docker web service with this repository's `Dockerfile`. Set `TOKENHARBOR_API_KEY` as a secret environment variable in Render. Render supplies `PORT` automatically.

The API permits browser requests from `https://snazzy-genie-1d91e5.netlify.app` and local Vite development at `http://localhost:5173`. After Render deploys, set `VITE_API_BASE_URL` in the Netlify site environment to the Render service's public origin (for example, `https://your-service.onrender.com`) and redeploy the frontend.
