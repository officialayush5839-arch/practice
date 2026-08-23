# ResumeIQ
**AI-Powered Resume Parsing & Candidate Screening**

ResumeIQ is a complete production-ready AI Resume Parser and Candidate Screening System. It processes PDF and DOCX resumes, extracts information via NLP, scores candidates against job requirements, and provides a polished, responsive HR dashboard for recruiters.

## Features
- **Smart Parsing**: Automatically extract structured candidate information from PDFs and DOCX files.
- **OCR Fallback**: When PDF text extraction fails (scanned docs), it uses OCR to extract text.
- **AI Skill Analysis**: Identifies and normalizes technical and professional skills using Regex and NLP.
- **ATS Matching Engine**: Scores candidates based on skills, experience, and keywords from the job description.
- **Candidate Ranking**: Priorities candidates based on transparent scoring.
- **Compare Candidates**: Compare candidates side-by-side to make better hiring decisions.

## Architecture
- **Frontend**: React, TypeScript, Vite, Tailwind CSS, React Router, Recharts
- **Backend**: Python, FastAPI, SQLAlchemy, Pydantic, Uvicorn
- **Database**: SQLite (default), extensible to PostgreSQL
- **Parsing**: PyMuPDF, python-docx, spaCy, pytesseract
- **Design Aesthetic**: Soft green background, rounded cards, minimal interface

## Installation

### Prerequisites
- Node.js 18+
- Python 3.10+
- Tesseract OCR (for OCR fallback)

### Environment Variables
Copy `.env.example` to `.env` and configure accordingly:
```bash
cp .env.example .env
```

### Backend Setup
1. Open terminal and navigate to the backend directory:
```bash
cd backend
```
2. Create and activate a virtual environment:
```bash
python -m venv venv
venv\Scripts\activate  # Windows
# source venv/bin/activate  # macOS/Linux
```
3. Install dependencies:
```bash
pip install -r requirements.txt
python -m spacy download en_core_web_sm
```
4. Run the backend server:
```bash
uvicorn app.main:app --reload
```
The API documentation will be available at `http://localhost:8000/docs`.

### Frontend Setup
1. Open a new terminal and navigate to the frontend directory:
```bash
cd frontend
```
2. Install dependencies:
```bash
npm install
```
3. Run the development server:
```bash
npm run dev
```

### Seeding Test Data
You can seed the database with sample jobs and candidates by running:
```bash
cd backend
python seed.py
```

## API Documentation
Once the backend is running, you can access the interactive API docs at:
- Swagger UI: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`

## Future Improvements
- Add authentication (OAuth/JWT)
- Implement cloud storage (AWS S3) for resumes
- Expand the LLM abstraction to use remote models (OpenAI, Anthropic) or local LLMs (Ollama)
