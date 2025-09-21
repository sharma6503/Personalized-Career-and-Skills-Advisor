# Personalized Career and Skills Advisor

### Overview
An AI-powered backend that helps users define career goals and generates **personalized skill-building plans, learning paths, and actionable steps**.  

---

## Features  
- Accepts high-level career goals (e.g., *“I want to become a Data Scientist”*)  
- Produces structured roadmaps with:  
  - Skills to acquire  
  - Recommended learning resources  
  - Step-by-step execution plan  
- Real-time **streaming responses** for continuous guidance  
- Configurable and easy to deploy in multiple environments  
- Built-in **health checks** and robust error handling  

---

## Tech Stack  
- **Backend:** Python  
- **Cloud:** Google Cloud (Vertex AI for deployment)  
- **Tooling:** `uv` for dependency management, Ruff + Mypy for linting and type-checking  

---

## Project Structure  
```
app/
  agent.py                 # Personalized Career & Skills Advisor logic
  agent_engine_app.py      # Cloud deployment helper
  config.py                # Environment and deployment configuration
  utils/                   # Cloud storage + tracing helpers

Makefile                   # install/dev/lint + deploy helper
pyproject.toml             # Python dependencies & linters
```

---

## Backend Logic  
- Core agent defined in `agent.py`  
- Converts **career goals → structured career roadmap**  
- Model defaults to **gemini-2.5-flash** (configurable via `.env`)  
- Generates both **long-term strategy** and **short-term actions**  

---

## Environment Setup  
`.env` file configuration:  

```bash
GOOGLE_CLOUD_PROJECT=your-gcp-project-id
GOOGLE_CLOUD_LOCATION=us-central1
GOOGLE_CLOUD_STAGING_BUCKET=my-staging-bucket

# Optional
MODEL=gemini-2.5-flash
AGENT_NAME=personalized-career-skills-advisor
```

---

## Run Locally  
```bash
make install
make dev-backend
```
Backend runs at:  
👉 `http://127.0.0.1:8000`  

---

## Deploy to Cloud  
Steps:  
1. Authenticate with Google Cloud:  
   ```bash
   gcloud auth application-default login
   gcloud config set project YOUR_PROJECT_ID
   ```  
2. Deploy the backend:  
   ```bash
   make deploy-adk
   ```  
3. Deployment metadata available at `logs/deployment_metadata.json`  

---

## Use Cases
- Personalized career roadmap generation  
- Skill-gap analysis and targeted learning suggestions  
- AI-driven mentorship for professional growth  
- Continuous progress tracking through interactive responses  

---

⚡ This backend is **hackathon-ready**: lightweight, cloud-deployable, and focused on solving a **real-world problem of career planning and skill development**.  
