# AI Server - Secure Document Search Portal

This is the AI team's part of the **AI-Powered Secure Document Search Portal** (Batch 1).

Employees upload private company documents and ask questions about them. This server reads the documents and gives answers based **only** on those files, using RAG (Retrieval-Augmented Generation) with the Google Gemini API.

## How it works

1. The Python team's backend sends a question to this server (`POST /ask`).
2. The server finds the most relevant parts of the uploaded documents.
3. The relevant parts and the question are sent to Gemini.
4. The server returns an answer based only on the documents. If the answer is not in them, it says "Not found".

## Tech used

- Python
- FastAPI
- Google Gemini API
- pypdf (reading PDF files)

## Setup

```bash
python -m venv venv
venv\Scripts\activate
pip install fastapi uvicorn google-generativeai python-dotenv pypdf
```

Create a `.env` file and add your key:

```
GEMINI_API_KEY=your_key_here
```

Never upload the `.env` file to GitHub.

## Run

```bash
uvicorn ai_server:app --port 8001 --reload
```

Then open `http://127.0.0.1:8001/docs` to test.

## Team

- AI team: this server (search and answers)
- Python team: backend (login, upload, storage)
- Web team: website
