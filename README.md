# Ascend-development

This repository contains the Ascend (Application Lifecycle Management) web application used by Ashok Leyland for requirements and workitem management. It includes a Python backend API and a TypeScript + Vite frontend application.

## Contents
- `backend/` — Python API and services (FastAPI-style app structure).
- `frontend/app/` — Vite + React/TypeScript single-page application.

## Prerequisites
- Python 3.8+ (use a virtual environment)
- Node.js 16+ and npm or yarn
- PostgreSQL 17

## Backend (backend)
1. Change to the backend directory:

	```bash
	cd backend
	```
2. Create and activate a virtual environment, then install dependencies:

	```bash
	python -m venv .venv
	# Windows
	.venv\Scripts\activate
	# macOS / Linux
	# source .venv/bin/activate
	pip install -r requirements.txt
	```
3. Run seeders to populate initial data. From the `backend/` folder in the activated virtual environment run:

	```bash
	python -m app.seeders.seed
	```
4. Run the backend API:

	```bash
	uvicorn app.main:app --reload
	```

Notes:
- The backend application code lives under `app/` and includes routers, models, services, and configuration.
- Configuration and database paths are in `app/config/` and auth helpers in `app/auth/`.

## Frontend (frontend/app)
1. Change to the frontend app directory:

	```bash
	cd frontend/app
	```
2. Install dependencies and run the dev server:

	```bash
	npm install
	npm run dev
	# or with yarn
	# yarn
	# yarn dev
	```

Notes:
- The frontend uses Vite + React + TypeScript. Environment variables are stored in `app/.env`.
- Source files are under `src/` (components, pages, config, redux slices, utils).

## Project Structure (high-level)
- `backend/` — Python backend; entry point `run.py` and app package `app/`.
- `frontend/app/` — Vite frontend app with `package.json` and `src/`.

## Running both locally
- Start the backend first (`uvicorn app.main:app --reload` from `backend/`).
- Start the frontend dev server (`npm run dev` from `frontend/app/`).

## Contributing
- Clone the repository and create feature branches.
- Keep changes focused and include tests where applicable.
