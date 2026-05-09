# Hacktiv8 Chatbot

A multimodal AI application built with **Google Gemini API** and **ExpressJS**, supporting text, image, document, and audio inputs.

## Overview

This application uses Google's Gemini 2.5 Flash model via the `@google/genai` SDK to generate content from various input types. Built on ExpressJS 5, it exposes a REST API for integrating AI-powered generation into any client.

## Tech Stack

- **Backend**: ExpressJS 5 (Node.js, ESM)
- **AI Engine**: Google Gemini 2.5 Flash (`@google/genai`)
- **File Uploads**: Multer
- **Environment Management**: dotenv

## Prerequisites

- **Node.js** (v18 or higher recommended)
- **npm**
- **Gemini API Key** from [Google AI Studio](https://aistudio.google.com/app/apikey)

## Installation

### 1. Clone the Repository

```bash
git clone <repository-url>
cd Hacktiv8_chat_bot
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Set Up Environment Variables

Create a `.env` file in the root directory:

```env
GEMINI_API_KEY=your_gemini_api_key_here
PORT=3000
```

### 4. Start the Server

```bash
node index.js
```

The server will start on `http://localhost:3000` (or your configured `PORT`).

## Project Structure

```
Hacktiv8_chat_bot/
├── assets/                # Sample assets (image, PDF)
├── node_modules/          # Installed dependencies
├── .env                   # Environment variables (create this)
├── .gitignore
├── index.js               # Main Express application & all routes
├── credential.md          # Credentials documentation
├── package.json
└── README.md
```

## API Endpoints

All endpoints return `{ result: string }` on success or `{ error: string }` on failure.

---

### Generate Text

**POST** `/generate-text`

**Content-Type:** `application/json`

**Request body:**
```json
{
  "prompt": "Your prompt here"
}
```

**Response:**
```json
{
  "result": "Generated text response"
}
```

---

### Generate from Image

**POST** `/generate-from-image`

**Content-Type:** `multipart/form-data`

| Field | Type | Description |
|-------|------|-------------|
| `prompt` | text | Prompt describing what to do with the image |
| `image` | file | Image file to analyze |

**Response:**
```json
{
  "result": "Generated text response based on the image"
}
```

---

### Generate from Document

**POST** `/generate-from-document`

**Content-Type:** `multipart/form-data`

| Field | Type | Description |
|-------|------|-------------|
| `prompt` | text | (Optional) Prompt; defaults to document summarization in Indonesian |
| `document` | file | Document file (e.g., PDF) to process |

**Response:**
```json
{
  "result": "Generated summary or response based on the document"
}
```

---

### Generate from Audio

**POST** `/generate-from-audio`

**Content-Type:** `multipart/form-data`

| Field | Type | Description |
|-------|------|-------------|
| `prompt` | text | (Optional) Prompt; defaults to transcription in Indonesian |
| `audio` | file | Audio file to transcribe or analyze |

**Response:**
```json
{
  "result": "Transcription or generated text from the audio"
}
```

---

## Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `GEMINI_API_KEY` | Google Gemini API key | Yes |
| `PORT` | Server port number | No (default: 3000) |

## Acknowledgments

- Google Gemini API for AI capabilities
- ExpressJS community
- Hacktiv8 for the opportunity
