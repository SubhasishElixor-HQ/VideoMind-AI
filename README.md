# 🎥 VideoMind AI

<p align="center">

<img src="https://img.shields.io/badge/AI-Video%20Intelligence-6366f1?style=for-the-badge" />
<img src="https://img.shields.io/badge/Python-3.11-3776AB?style=for-the-badge&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" />
<img src="https://img.shields.io/badge/Whisper-Speech%20to%20Text-8B5CF6?style=for-the-badge" />
<img src="https://img.shields.io/badge/LangChain-RAG-1C3C3C?style=for-the-badge" />

</p>

<p align="center">
  <b>Transform long videos and meetings into searchable, actionable intelligence.</b>
</p>

<p align="center">
  Upload a video, audio file, or provide a YouTube URL — VideoMind AI transcribes,
  summarizes, extracts important information, and lets you chat with the content.
</p>

---

## ✨ What is VideoMind AI?

**VideoMind AI** is an AI-powered video and meeting intelligence system designed to convert unstructured video/audio content into structured knowledge.

Instead of manually watching a long meeting or lecture, users can:

```text
Video / Audio / YouTube
        │
        ▼
   Audio Processing
        │
        ▼
   Whisper Transcription
        │
        ▼
   Transcript
        │
        ├───────────────┐
        ▼               ▼
   AI Analysis       Vector Store
        │               │
        ├── Summary     ▼
        ├── Actions    RAG
        ├── Decisions   │
        ├── Questions   ▼
        └── Title      AI Chat
```

---

# 🚀 Features

### 🎬 Video & Audio Processing

* Upload local video/audio files
* Process YouTube URLs
* Extract audio from videos
* Split audio into manageable chunks

### 🎙️ AI Transcription

Powered by **OpenAI Whisper**.

* Speech-to-text transcription
* Local transcription
* Supports multilingual audio
* English / Hinglish workflow

### 🧠 Intelligent Summarization

Generate:

* Meeting summary
* Important topics
* Key information
* AI-generated title

### ✅ Action Item Extraction

Automatically identify:

```text
Task
Person
Deadline
Status
```

Example:

> Prepare the project presentation by Friday.

### 🔑 Key Decision Extraction

Extract important decisions made during a meeting.

Example:

```text
Decision:
Use FastAPI as the backend framework.
```

### ❓ Open Question Extraction

Identify unanswered questions and unresolved topics.

### 💬 Chat with Your Meeting

Ask questions about the transcript using RAG.

Example:

```text
You:
What did the team decide about the backend?

AI:
The team decided to use FastAPI as the backend framework.
```

The assistant is instructed to answer using the meeting transcript context.

---

# 🏗️ System Architecture

```text
                    ┌──────────────────────┐
                    │      User Input      │
                    │                      │
                    │ Video / Audio / URL  │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Audio Processor    │
                    │                      │
                    │ Download / Extract   │
                    │ Chunk Audio          │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Whisper Engine     │
                    │                      │
                    │ Speech → Text        │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │     Transcript       │
                    └──────────┬───────────┘
                               │
              ┌────────────────┼─────────────────┐
              │                │                 │
              ▼                ▼                 ▼
       ┌────────────┐   ┌────────────┐   ┌────────────┐
       │ Summarizer │   │ Extractor  │   │ Vector DB  │
       └──────┬─────┘   └──────┬─────┘   └──────┬─────┘
              │                │                 │
              ▼                ▼                 ▼
          Summary       Actions / Decisions     RAG
                       / Questions               │
                                                 ▼
                                        ┌────────────────┐
                                        │   Mistral AI   │
                                        └───────┬────────┘
                                                │
                                                ▼
                                        ┌────────────────┐
                                        │ AI Meeting Chat│
                                        └────────────────┘
```

---

# 🧩 Core Pipeline

```text
INPUT
  │
  ▼
Video / Audio / YouTube
  │
  ▼
Audio Processing
  │
  ▼
Whisper
  │
  ▼
Transcript
  │
  ├──────────────► Summary
  │
  ├──────────────► Title
  │
  ├──────────────► Action Items
  │
  ├──────────────► Key Decisions
  │
  ├──────────────► Open Questions
  │
  ▼
Embedding
  │
  ▼
ChromaDB
  │
  ▼
Retriever
  │
  ▼
Mistral AI
  │
  ▼
Context-Aware Answer
```

---

# 🛠️ Tech Stack

| Technology               | Purpose                                    |
| ------------------------ | ------------------------------------------ |
| 🐍 Python 3.11           | Core programming language                  |
| 🎙️ OpenAI Whisper       | Speech-to-text                             |
| 🧠 Mistral AI            | LLM processing                             |
| 🔗 LangChain             | AI/RAG orchestration                       |
| 🗄️ ChromaDB             | Vector database                            |
| 🔎 Sentence Transformers | Embeddings                                 |
| 🎨 Streamlit             | Web interface                              |
| 🎬 yt-dlp                | YouTube processing                         |
| 🔊 Pydub                 | Audio processing                           |
| ⚡ uv                     | Python environment & dependency management |
| 🎵 FFmpeg                | Audio/video processing                     |

---

# 📁 Project Structure

```text
VideoMind-AI/
│
├── .python-version
├── .env
├── .gitignore
├── pyproject.toml
├── requirements.txt
├── uv.lock
│
├── app.py
├── main.py
│
├── core/
│   ├── __init__.py
│   ├── rag_engine.py
│   ├── vector_store.py
│   ├── transcriber.py
│   ├── summarizer.py
│   └── extractor.py
│
├── utils/
│   ├── __init__.py
│   └── audio_processor.py
│
└── README.md
```

---

# ⚙️ Installation

## 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/VideoMind-AI.git
cd VideoMind-AI
```

---

## 2. Install Python 3.11

VideoMind AI currently uses **Python 3.11**.

With `uv`:

```powershell
uv python install 3.11
```

Pin the project to Python 3.11:

```powershell
uv python pin 3.11
```

Verify:

```powershell
uv run python --version
```

Expected:

```text
Python 3.11.x
```

---

# 🧪 Create Virtual Environment

Create the environment:

```powershell
uv venv --python 3.11
```

If an old environment exists:

```powershell
Remove-Item -Recurse -Force .venv
uv venv --python 3.11
```

---

# 📦 Install Dependencies

Using the project configuration:

```powershell
uv sync
```

Or install from `requirements.txt`:

```powershell
uv pip install -r requirements.txt
```

---

# 🔐 Environment Variables

Create a `.env` file in the project root:

```env
MISTRAL_API_KEY=your_mistral_api_key
```

Never commit your real API key.

Your `.gitignore` should contain:

```gitignore
.env
.venv/
__pycache__/
*.pyc
```

---

# 🎵 Install FFmpeg

VideoMind AI requires FFmpeg for audio/video processing.

### Windows

```powershell
winget install Gyan.FFmpeg
```

Restart PowerShell and verify:

```powershell
ffmpeg -version
```

If the command displays FFmpeg information, installation is successful.

---

# ▶️ Run the Application

From the project root:

```powershell
uv run streamlit run app.py
```

Streamlit will provide a local address similar to:

```text
http://localhost:8501
```

Open it in your browser.

---

# 🖥️ Alternative: Run CLI

You can also run the pipeline through `main.py`:

```powershell
uv run python main.py
```

Then enter:

```text
Enter YouTube URL or local file path:
```

For example:

```text
https://www.youtube.com/watch?v=XXXXXXXX
```

Then select:

```text
english
```

or:

```text
hinglish
```

---

# 🔄 How to Use

## Step 1 — Provide Input

Choose one:

```text
🎬 Video file
🎵 Audio file
🔗 YouTube URL
```

---

## Step 2 — Processing

VideoMind AI processes the content:

```text
Input
 ↓
Audio Extraction
 ↓
Audio Chunking
 ↓
Whisper Transcription
 ↓
Transcript
```

---

## Step 3 — AI Analysis

The transcript is analyzed to generate:

```text
📌 Title

📋 Summary

✅ Action Items

🔑 Key Decisions

❓ Open Questions
```

---

## Step 4 — Ask Questions

The transcript is converted into searchable vector representations.

```text
Transcript
    ↓
Chunks
    ↓
Embeddings
    ↓
ChromaDB
    ↓
Retriever
    ↓
Relevant Context
    ↓
Mistral AI
    ↓
Answer
```

You can then ask questions such as:

```text
What were the main topics discussed?

What decisions were made?

Who was assigned the presentation?

What are the open questions?

What deadline was mentioned?
```

---

# 🧠 RAG Architecture

VideoMind AI uses **Retrieval-Augmented Generation (RAG)** for transcript-based conversation.

```text
User Question
      │
      ▼
   Retriever
      │
      ▼
ChromaDB
      │
      ▼
Relevant Transcript Chunks
      │
      ▼
Context + Question
      │
      ▼
Mistral AI
      │
      ▼
Final Answer
```

The RAG prompt instructs the model to use the meeting transcript as its source of context.

If the requested information cannot be found, the assistant should respond:

```text
I could not find this information in the meeting transcript.
```

---

# 🧪 Testing

Test Python:

```powershell
uv run python --version
```

Test LangChain:

```powershell
uv run python -c "from langchain_core.runnables import RunnablePassthrough, RunnableLambda; print('LANGCHAIN CORE OK')"
```

Test PyTorch:

```powershell
uv run python -c "import torch; print('TORCH OK:', torch.__version__)"
```

Test FFmpeg:

```powershell
ffmpeg -version
```

---

# ⚠️ Troubleshooting

## PyTorch — WinError 4551

If you see:

```text
OSError: [WinError 4551] An Application Control policy has blocked this file.
```

with:

```text
torch_global_deps.dll
```

this indicates a Windows Application Control/Code Integrity restriction affecting a PyTorch native DLL.

Check Windows Event Viewer:

```text
Event Viewer
 → Applications and Services Logs
 → Microsoft
 → Windows
 → CodeIntegrity
 → Operational
```

Do not repeatedly reinstall PyTorch for this error; the underlying Windows policy needs to be addressed.

---

## FFmpeg Not Found

If you see:

```text
Couldn't find ffmpeg or avconv
```

install FFmpeg:

```powershell
winget install Gyan.FFmpeg
```

Then restart PowerShell and verify:

```powershell
ffmpeg -version
```

---

## Wrong Virtual Environment

If you see:

```text
VIRTUAL_ENV=...\OneDrive\...\VideoMind-AI\.venv
does not match the project environment path
```

deactivate the old environment:

```powershell
deactivate
```

Then move to the correct project:

```powershell
cd C:\Dev\VideoMind-AI
```

Verify:

```powershell
uv run python -c "import sys; print(sys.executable)"
```

Expected:

```text
C:\Dev\VideoMind-AI\.venv\Scripts\python.exe
```

---

# 🔒 Security

Never commit secrets to GitHub.

Do **not** commit:

```text
.env
API keys
tokens
passwords
private credentials
```

Use environment variables:

```env
MISTRAL_API_KEY=your_key
```

---

# 🚧 Current Limitations

* Local Whisper requires PyTorch.
* Video processing can require significant CPU/RAM.
* Large videos take longer to transcribe.
* YouTube processing depends on external availability and `yt-dlp`.
* AI-generated summaries and extracted information should be reviewed by the user.
* The RAG system is limited to information available in the processed transcript.

---

# 🗺️ Roadmap

### Phase 1 — Core

* [x] Video/audio input
* [x] YouTube input
* [x] Whisper transcription
* [x] AI summary
* [x] Title generation
* [x] Action item extraction
* [x] Decision extraction
* [x] Question extraction

### Phase 2 — Intelligence

* [x] Vector database
* [x] RAG pipeline
* [x] Transcript chat
* [ ] Speaker identification
* [ ] Timestamp-based answers
* [ ] Better multilingual support

### Phase 3 — Productivity

* [ ] Export meeting notes
* [ ] PDF reports
*
