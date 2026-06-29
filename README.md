# Agentic Data Modelling with AI

A modern, AI-assisted data modelling experience that turns natural language requirements into a reviewable logical model, a physical schema, SQL, and an ERD.

This project combines a React frontend with a FastAPI backend and Azure-backed AI services to help teams move from idea to database design faster and with less friction.

![Product Preview](https://img.shields.io/badge/Status-Active-success) ![Python](https://img.shields.io/badge/Python-3.11-blue) ![React](https://img.shields.io/badge/React-19-61DAFB) ![FastAPI](https://img.shields.io/badge/FastAPI-0.104-009688)

## Why this project exists

Designing a database schema often means switching between requirements notes, modelling tools, SQL editors, and diagramming software. This app brings those steps together in one flow:

- Describe the system or business need in plain English
- Review the generated logical model
- Approve or refine the physical model
- Validate the design and generate SQL
- Create an ERD for visualization

## Key features

- Natural-language-to-schema generation
- Logical model review before physical modelling
- Validation and SQL generation workflow
- ERD generation from SQL
- Support for multiple database targets and modelling styles
- Azure OpenAI + Azure AI Search integration for smarter context-aware generation

## Tech stack

- Frontend: React + Vite
- Backend: FastAPI + Pydantic
- Workflow orchestration: LangGraph
- AI services: Azure OpenAI, Azure AI Search
- Data modelling: Python-based schema generation and validation pipeline

## Project structure

```text
backend/          # FastAPI API, agents, graph workflow, RAG logic
frontend/         # React/Vite user interface
requirements.txt  # Root-level Python dependencies
```

## Prerequisites

Before running the app locally, make sure you have:

- Python 3.11+
- Node.js 18+
- npm or pnpm
- Access to Azure OpenAI and Azure AI Search

## Environment variables

Create a `.env` file in the project root or inside the backend folder with the following values:

```env
AZURE_OPENAI_ENDPOINT=https://<your-resource>.openai.azure.com/
AZURE_OPENAI_API_KEY=<your-azure-openai-key>
AZURE_OPENAI_DEPLOYMENT=<your-chat-deployment>
AZURE_OPENAI_API_VERSION=2024-02-01

AZURE_SEARCH_ENDPOINT=https://<your-search-service>.search.windows.net
AZURE_SEARCH_ADMIN_KEY=<your-search-admin-key>
EMBEDDING_DEPLOYMENT=<your-embedding-deployment>
```

> If your local environment uses a slightly different Azure Search variable name, keep it consistent with the codebase you are running.

## Quick start

### 1) Clone the repository

```bash
git clone https://github.com/shruu27/Data-Modelling-Agentic-AI.git
cd Data-Modelling-Agentic-AI
```

### 2) Set up the backend

On Windows PowerShell:

```powershell
py -3.11 -m venv venv3
.\venv3\Scripts\Activate.ps1
pip install -r requirements.txt
pip install -r backend\requirements.txt
```

Run the API:

```bash
uvicorn backend.main:app --reload --host 0.0.0.0 --port 8000
```

### 3) Set up the frontend

```bash
cd frontend
npm install
npm run dev
```

The frontend will usually be available at:

```text
http://localhost:5173
```

## How the app works

1. Enter a business requirement or data modelling prompt.
2. The backend generates a logical model for review.
3. You approve the logical model and the system creates a physical model.
4. The app validates the model and generates SQL.
5. An ERD can be generated from the resulting SQL.

## Example use cases

- Generate a schema for an e-commerce platform
- Model a subscription or billing system
- Create a relational design from a product requirement document
- Convert an existing concept into SQL and ERD assets

