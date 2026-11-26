<div align="center">

# 🧠 Neural Vault

### AI Neural Database — Store & Search Any Data Type by Meaning, Not Keywords

[![FastAPI](https://img.shields.io/badge/Backend-FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![React](https://img.shields.io/badge/Frontend-React-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://reactjs.org/)
[![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Gemini](https://img.shields.io/badge/AI-Google%20Gemini-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://deepmind.google/technologies/gemini/)
[![TailwindCSS](https://img.shields.io/badge/UI-TailwindCSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)

**Powered by Gemini embeddings + pgvector. Unifies vectors, documents, code, images, audio, graphs & reasoning traces in one semantic engine. Build your AI's memory layer — no GPU required.**

</div>

---

## 📖 What is Neural Vault?

Traditional databases search by **exact match**. Neural Vault searches by **meaning**. 

Ask *"show me code about authentication"* and it finds relevant snippets — even if the word "authentication" never appears in the code. It acts as a single, unified memory layer for AI systems, storing and connecting multiple data modalities.

## ✨ Key Features

- 🔢 **8 Data Types in One Engine**: Vectors, Documents, Code, Images, Audio, Knowledge Graphs, and AI Reasoning Traces.
- 🔍 **Unified Semantic Search**: Query everything at once. Get results grouped by type based on semantic similarity.
- 🧠 **Gemini-Powered**: Auto-generates 768-dimension embeddings via Google Gemini API.
- 🖼️ **AI-Generated Metadata**: Automatically generates descriptions for images and transcripts for audio.
- 🕸️ **Knowledge Graph**: Store nodes and relationships with semantic linking.
- 🧩 **Reasoning Traces**: Save step-by-step AI thinking processes for explainability.
- 💻 **CPU-Friendly**: Runs perfectly on any standard laptop. No GPU required.
- 🎨 **Premium UI**: Beautiful, AI-native dashboard built with React + TailwindCSS.

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| **Backend** | Python, FastAPI, SQLAlchemy, Alembic |
| **Frontend** | React, Vite, TailwindCSS, Framer Motion |
| **Database** | PostgreSQL + `pgvector` extension |
| **AI / Embeddings** | Google Gemini API (`text-embedding-004`, `gemini-1.5-flash`) |

## 🏗️ Architecture

```text
[ React Frontend ] 
       ⬇ (REST API)
[ FastAPI Backend ] 
       ⬇ (SQLAlchemy ORM)
[ PostgreSQL + pgvector ] 
       ⬆ (Semantic Search)
[ Gemini Embeddings ]


# Create database
psql -U postgres -c "CREATE DATABASE neural_vault;"

# Connect and enable pgvector
psql -U postgres -d neural_vault -c "CREATE EXTENSION IF NOT EXISTS vector;"


cd backend
python -m venv venv
# Windows: venv\Scripts\activate | Mac/Linux: source venv/bin/activate
pip install -r requirements.txt

# Create .env file and add your keys
# GEMINI_API_KEY=your_key_here
# DATABASE_URL=postgresql://postgres:password@localhost:5432/neural_vault

# Run migrations
alembic upgrade head

# Start server
uvicorn app.main:app --reload


cd frontend
npm install
npm run dev