# Intelligent Recruitment System
**AI-driven candidate evaluation using a modular multi-agent architecture**

---

## Overview

Intelligent Recruitment System is a production-oriented AI backend that automates **resume screening and candidate evaluation** against a given job description.

The system processes resumes through **specialized agents**, each responsible for a specific evaluation dimension, and generates a **structured, explainable hiring report**.

---

## Key Capabilities

- Automated resume parsing (PDF → structured data)
- Multi-agent candidate evaluation
- Skill gap analysis
- Experience and education validation
- Red flag detection (gaps, inconsistencies)
- AI-generated interview questions
- Salary estimation
- Final candidate scoring (0–100) with recommendation

---

## Architecture

The system follows a **modular multi-agent design**:

- Independent agents for each evaluation dimension  
- Parallel execution for performance  
- JSON-based communication between components  
- Central synthesis layer for final decisioning  

### Agents

- Resume Parsing Agent  
- Skills Matching Agent  
- Experience Analysis Agent  
- Education Validation Agent  
- Culture Fit Agent  
- Red Flag Agent  
- Interview Recommendation Agent  
- Salary Estimation Agent  
- Synthesis Agent  

---

## Workflow

1. Resume uploaded (PDF)  
2. Resume Parsing Agent extracts structured data  
3. Job description provided as input  
4. Evaluation agents run in parallel  
5. Synthesis Agent aggregates outputs  
6. Final structured report generated  

Refer to `/asset/recruitment_data_flow.svg` for visual representation

---

## API Endpoints

| Method | Endpoint        | Description                     |
|--------|----------------|---------------------------------|
| POST   | `/evaluate`     | Evaluate resume against job     |
| POST   | `/parse-resume` | Extract structured resume data  |
| GET    | `/health`       | Service health check            |

---

## Sample Request

### `/evaluate`

```json
{
  "job_title": "Backend Engineer",
  "job_description": "Experience with FastAPI, Python, and REST APIs",
  "resume": "<PDF_FILE>"
}
```

---

## Sample Response

```json
{
  "score": 82,
  "recommendation": "Strong Fit",
  "matched_skills": ["Python", "FastAPI", "REST APIs"],
  "missing_skills": ["Docker"],
  "summary": "Candidate demonstrates strong backend experience with relevant frameworks."
}
```

---

## Tech Stack

| Layer         | Technology           |
|---------------|---------------------|
| Backend       | FastAPI             |
| LLM           | HuggingFace Models  |
| Orchestration | LangChain           |
| Parsing       | pdfplumber / pypdf  |
| Database      | SQLite              |
| Frontend      | Streamlit           |

---

## Setup

```bash
git clone https://github.com/your-username/intelligent-recruitment-system.git
cd intelligent-recruitment-system

pip install -r requirements.txt
uvicorn backend.main:app --reload
```

---

## Demo

- Frontend UI: `/frontend/` (placeholder)  
- Workflow Diagram: `/assets/workflow.svg`  

> Add screenshots or demo GIFs here

---

## Design Principles

- **Modularity** — independent agent design  
- **Explainability** — transparent scoring and reasoning  
- **Scalability** — parallel execution of agents  
- **Simplicity** — minimal infrastructure, fast iteration  

---

## Future Improvements

- Multi-candidate ranking system  
- Advanced LLM fine-tuning for domain roles  
- Real-time dashboard for HR analytics  
- Cloud deployment with scaling support  
- Integration with ATS platforms  

---

## Project Status

**MVP Complete — Backend Fully Functional**

---

## License

MIT License
