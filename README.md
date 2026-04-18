# Rabit Docs

This Mintlify workspace lives inside the Rabit backend repository and is used to preview and publish product documentation.

## Run locally

### Preview the docs site

Install the Mintlify CLI:

```bash
npm i -g mint
```

From the `.doch` directory, start the local docs preview:

```bash
mint dev
```

The docs preview is available at:

- `http://localhost:3000`

### Run the Rabit backend locally

From the repository root:

1. Create and activate a virtual environment
2. Install backend dependencies
3. Copy `.env.example` to `.env`
4. Start the API server

Example:

```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
python main.py
```

Optional Drift read-only dependencies:

```bash
pip install -r requirements-drift-readonly.txt
```

The backend runs at:

- `http://localhost:8000`

Useful local URLs:

- Swagger UI: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`
- Health: `http://localhost:8000/api/health`

## Typical local workflow

Use two terminals:

1. backend API from the repo root
2. Mintlify docs preview from `.doch`

That gives you:

- backend on `:8000`
- docs on `:3000`

## Troubleshooting

- If `mint dev` fails, run `mint update`
- If a docs page 404s, make sure you are inside `.doch` where `docs.json` exists
- If the backend fails to start, review `.env` values for:
  - `ANTHROPIC_API_KEY` or OpenRouter settings
  - `AUTH_JWT_SECRET`
  - `DRIFT_RPC_URL`
  - `BACKPACK_API_URL`
