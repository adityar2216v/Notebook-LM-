<div align="center">
  <img src="https://img.icons8.com/color/96/000000/google-keep.png" alt="NotebookLM Logo">
  <h1>🧠 NotebookLM Clone - Your AI Research Assistant</h1>
  <p>
    <em>An exact, open-source replica of Google NotebookLM. Supercharge your research, generate podcasts, study aids, and chat directly with your documents.</em>
  </p>
  
  <p>
    <a href="https://www.python.org/"><img src="https://img.shields.io/badge/Python-3.9+-blue.svg" alt="Python"></a>
    <a href="https://flask.palletsprojects.com/"><img src="https://img.shields.io/badge/Flask-000000?style=flat&logo=flask&logoColor=white" alt="Flask"></a>
    <a href="https://ai.google.dev/"><img src="https://img.shields.io/badge/Gemini_Pro-4285F4?style=flat&logo=google&logoColor=white" alt="Gemini API"></a>
    <a href="https://supabase.com/"><img src="https://img.shields.io/badge/Supabase-3ECF8E?style=flat&logo=supabase&logoColor=white" alt="Supabase pgvector"></a>
  </p>
</div>

<br />

> **Welcome to the ultimate open-source NotebookLM experience!** Upload your PDFs, text files, and notes, and let our advanced AI synthesize the information, ground answers in citations, and even generate a lively audio podcast about your research!

---

## 🎨 Application Interface

Experience a sleek, modern interface meticulously designed to replicate the beloved Google NotebookLM experience. 

![NotebookLM GUI](static/gui_mockup.png)
*(A look at the interactive dashboard where you can chat, listen, and learn)*

---

## ✨ Key Features

Our replica doesn't just look the part; it is packed with cutting-edge AI capabilities:

* **💬 Source-Grounded Chat**: Ask questions and get answers *only* based on the documents you upload. No hallucinations!
* **🎧 Audio Overviews (Podcasts)**: Instantly convert your research into an engaging, conversational, two-host podcast using `edge-tts`.
* **🧠 Auto-Generated Study Aids**: One-click generation of Flashcards, Quizzes, and Mermaid.js Flowcharts based on your sources.
* **📽️ Video Presentation Generation**: Automatically generates slide decks and MP4 video presentations complete with AI narration.
* **🗃️ Vector Database Integration**: Utilizes PostgreSQL with `pgvector` (via Supabase) for lightning-fast semantic search.
* **📄 Multi-Format Support**: Upload `.txt` and `.pdf` files seamlessly.

---

## 🛠️ Technology Stack

| Component | Technology | Description |
| :--- | :--- | :--- |
| **Backend Framework** | [Flask](https://flask.palletsprojects.com/) | Robust Python web server handling API routes and logic. |
| **LLM Engine** | [Google Gemini](https://ai.google.dev/) | Utilizing `gemini-1.5-pro` for text generation and embeddings. |
| **Vector Storage** | [Supabase (pgvector)](https://supabase.com/) | PostgreSQL database optimized for highly scalable similarity search. |
| **Audio/TTS** | [Edge-TTS](https://github.com/rany2/edge-tts) / gTTS | High-quality Neural Text-to-Speech generation. |
| **Media Processing** | [MoviePy](https://zulko.github.io/moviepy/) / Pillow | Creating dynamic slides and composing video assets. |

---

## 🚀 Getting Started

Follow these instructions to get a copy of the project up and running on your local machine.

### 1. Prerequisites
Ensure you have the following installed:
- **Python 3.9+**
- **FFmpeg** (Required for Audio/Video processing)
- A **Supabase** account (for PostgreSQL database)
- A **Google Gemini API Key**

### 2. Clone the Repository
```bash
git clone https://github.com/your-username/Notebook-LM-.git
cd Notebook-LM-
```

### 3. Environment Setup
Create a virtual environment to manage dependencies:
```bash
python -m venv venv
# On Windows:
.\venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

Install the required packages:
```bash
pip install -r requirements.txt
```

### 4. Configuration
Create a `.env` file in the root directory (this is ignored by Git to keep your secrets safe). Add your API keys and DB credentials:

```env
SECRET_KEY=your_secure_flask_secret_key
GEMINI_API_KEY=your_google_gemini_api_key
DATABASE_URL=postgresql://postgres:your_password@db.your-project.supabase.co:5432/postgres
```

### 5. Initialize the Database
The application will automatically attempt to initialize your Supabase PostgreSQL database with the required `pgvector` extension and schema upon the first connection.

### 6. Run the Application!
Start the Flask development server:
```bash
python app.py
```
*(Or `flask run`)*

Navigate to `http://localhost:5000` in your web browser and start uploading your documents!

---

## 🏗️ Project Architecture

```text
📁 Notebook-LM-/
│
├── 📄 app.py                  # Main Flask application, routes, and DB initialization
├── 📄 config.py               # Configuration loading from environment variables
├── 📄 list_models.py          # Utility script to check available Gemini models
├── 📄 requirements.txt        # Python dependencies
├── 📄 .env                    # Environment variables (do not commit!)
├── 📁 static/                 
│   ├── 📄 style.css           # UI Styling (NotebookLM replica theme)
│   ├── 📄 script.js           # Frontend logic (chat, uploading, media generation)
│   └── 🖼️ gui_mockup.png      # Screenshots for README
└── 📁 templates/              
    └── 📄 index.html          # Main application HTML structure
```

---

## 🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

<div align="center">
  Built with ❤️ for AI researchers and students everywhere.
</div>
