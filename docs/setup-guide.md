# Setup Guide

> **This file is read by the automated evaluation pipeline. Be precise and complete.**

## Prerequisites

Before you begin, ensure you have the following installed:

- [ ] Python 3.11+
- [ ] Node.js 18+
- [ ] Docker Desktop
- [ ] An IBM Cloud account with watsonx.ai access

## Environment Variables

Copy `.env.example` to `.env` and fill in the values:

```bash
cp .env.example .env
# 1. Clone the repository
git clone https://github.com/26ec111-dotcom/bob-ai-hackthone--H4X.git
cd bob-ai-hackthone--H4X

# 2. Install backend dependencies
pip install -r requirements.txt

# 3. Install frontend dependencies
cd frontend
npm install
cd ..

# 4. Set up the database
docker compose up -d db
# Start the backend
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000

# Start the frontend in a separate terminal
cd frontend
npm run dev

pytest tests/ -v

# Start the database
docker compose up -d db

# Start the backend
uvicorn app.main:app --reload --port 8000

# Start the frontend in a separate terminal
cd frontend
npm run dev
