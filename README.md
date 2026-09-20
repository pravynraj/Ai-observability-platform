# AI Assistant Observability & Evaluation Platform

A full-stack observability platform for monitoring AI assistant requests, latency, token usage, cost, and response quality.

## Project structure

- `frontend/` — React + TypeScript dashboard UI
- `backend/` — FastAPI telemetry API and SQLite/PostgreSQL-ready models
- `docs/` — architecture and API notes
- `ai-assistant/` — demo assistant integration scaffolding
- `observability/` — telemetry/monitoring configuration notes
- `database/` — schema and migration notes

## Goals

- End-to-end AI request tracing
- Dashboard overview for success rate, latency, cost, and errors
- Live demo assistant with generated telemetry
- API endpoints for traces, costs, metrics, tools, and alerts
- Database design aligned to Postgres-based observability workloads

## Local setup

1. Start PostgreSQL if you want to use the Postgres connection:
   `docker compose up -d`
2. Activate the Python environment and install backend dependencies:
   `cd backend && ../.venv/Scripts/python.exe -m pip install -r requirements.txt`
3. Launch the API:
   `../.venv/Scripts/python.exe -m uvicorn app.main:app --reload --host 0.0.0.0 --port 8000`
4. Launch the frontend:
   `cd frontend && npm install && npm run dev -- --host 0.0.0.0`

The backend defaults to a SQLite file in the repo (`ai_observability.db`) when no `DATABASE_URL` is set, which makes local development simple while still supporting PostgreSQL configuration.

## Demo workflow

1. Open the frontend dashboard.
2. Ask the demo assistant a question in the chat panel.
3. A trace, model call, token and latency records, cost metadata, and evaluation score are generated automatically.
4. Use the dashboard to inspect traces, metrics, tools, and errors.

## MVP delivered

- AI chatbot demo
- Trace ID generation
- Latency and token tracking
- Cost estimation
- Error monitoring
- Dashboard + trace explorer
- PostgreSQL-ready data model
