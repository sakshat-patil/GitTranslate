# GitTranslate

A full-stack web app for translating and localizing content using OpenAI’s APIs.  
GitTranslate lets you:

Devpost: [https://devpost.com/software/gitcast](https://devpost.com/software/gitcast)

- **Fetch and browse** Git repositories (GitHub, GitLab)
- **Translate** code comments, filenames, and documentation into your chosen language via GPT-3.5 Turbo
- **(Bonus)** Upload podcast or other audio files to **transcribe** with Whisper, **translate** the transcript, and **synthesize** new audio in the target language
- **Deploy** easily: frontend on Vercel, backend on any Python-friendly host (Heroku, AWS, etc.)
- **Automate** workflows with the included Orkes FE script

<br />

## Demo

Live at: [git-translate-indol.vercel.app](https://git-translate-indol.vercel.app)

<br />

## Features

- **Frontend**: Next.js + React + TypeScript + Tailwind CSS  
- **Backend**: Python (FastAPI)  
- **Audio**: Whisper for transcription, TTS for speech synthesis  
- **Translation**: OpenAI GPT-3.5 Turbo for text translation  
- **Workflow**: scripts/orkes-fe-script.py for Orkes integration  
- **Configurable**: .env-driven, ready for local or cloud deployment  

<br />

## Table of Contents

1. Getting Started
2. Prerequisites
3. Installation
4. Configuration
5. Running Locally
6. Deployment
7. Project Structure
8. Contributing
9. License

<br />

---

## Getting Started

### Prerequisites

- Node.js v16+
- Python 3.9+
- A valid OpenAI API Key

### Installation

1. Clone this repo  
   ```
   git clone https://github.com/sakshat-patil/GitTranslate.git
   cd GitTranslate
   ```

2. Backend  
   ```
   cd backend
   python -m venv venv
   source venv/bin/activate   # or venv\Scripts\activate on Windows
   pip install -r requirements.txt
   ```

3. Frontend  
   ```
   cd ../frontend
   npm install
   ```

<br />

## Configuration

Copy the example .env files and fill in your keys:

```
# backend/.env
OPENAI_API_KEY=your_openai_api_key
PORT=8000

# frontend/.env.local
NEXT_PUBLIC_API_BASE_URL=http://localhost:8000
```

<br />

## Running Locally

1. Start the backend (FastAPI + Uvicorn)  
   ```
   cd backend
   uvicorn app.main:app --reload --host 0.0.0.0 --port ${PORT:-8000}
   ```

2. Start the frontend (Next.js)  
   ```
   cd ../frontend
   npm run dev
   ```

Visit http://localhost:3000 in your browser and you’re live.

<br />

## Deployment

- Frontend: Push to Git, deploy via Vercel (auto-detect Next.js).
- Backend: Containerize or push to any Python host (Heroku, AWS Elastic Beanstalk, etc.).
- Workflows: See scripts/orkes-fe-script.py for setting up Orkes flows.

<br />

## Project Structure

```
/
├── backend/               # FastAPI app
│   ├── app/
│   ├── requirements.txt
│   └── .env
├── frontend/              # Next.js + React UI
│   ├── pages/
│   ├── components/
│   ├── public/
│   └── .env.local
├── scripts/
│   └── orkes-fe-script.py # Orkes workflow helper
├── LICENSE
└── sample.txt             # Example input/output
```

<br />

## Contributing

1. Fork the repo
2. Create a feature branch (git checkout -b feat/my-feature)
3. Commit your changes (git commit -m "feat: add X")
4. Push and open a PR

Please follow the existing code style and include tests where applicable.

<br />

## License

This project is licensed under the MIT License  
See LICENSE for details.
