# 🎓 PARCOURS-AI

> **Plateforme Intelligente d'Orientation Scolaire & Professionnelle au Bénin**  
> *Développée dans le cadre du Challenge **Ignite Your Future**.*
Lien : https://parcours-ai.vercel.app/

---

##  Présentation

**PARCOURS-AI** est une solution guidant les bacheliers et étudiants béninois vers les filières et métiers les plus adaptés à leur profil, tout en éliminant les risques d'hallucinations sur les frais de scolarité et les cursus universitaires réels.

###  Points Forts
- **Zéro hallucination** : Catalogue national intégré de **530+ filières réelles** avec frais exacts en FCFA (universités publiques et privées).
- **Matching déterministe à 5 dimensions** : Intérêts (30%), Série du Bac (25%), Notes clés (20%), Budget annuel (15%), Localisation (10%).
- **RAG Web en temps réel** : Recherche d'actualités et d'opportunités via **Tavily** / **DuckDuckGo**, filtrées sur les sources officielles (`.gouv.bj`, `.edu.bj`, `.bj`).
- **Résilience IA** : Modèle principal **Gemini 2.0 Flash** couplé à un moteur local de secours (fallback 100% fonctionnel hors-ligne).
- **Export & Restitution** : Diagnostic personnalisé téléchargeable en PDF.

---

##  Stack Technique

| Composant | Technologies |
| :--- | :--- |
| **Frontend** | React 19, TypeScript, Vite, Tailwind CSS v4, Motion, Lucide Icons |
| **Backend** | FastAPI, Python 3.11+, Uvicorn, Pydantic v2, SlowAPI |
| **IA & RAG** | Google Gemini 2.0 Flash, Tavily Search API / DuckDuckGo Scraper |
| **BaaS / Auth** | Supabase (Authentification Email / Téléphone OTP / Google) |

---

##  Démarrage Rapide

### Option 1 : Lancement en 1 clic (Windows)
```cmd
start_project.bat
```
*(ou avec PowerShell : `./start_project.ps1`)*

---

### Option 2 : Lancement manuel

#### 1. Backend (FastAPI)
```bash
cd backend
python -m venv .venv

# Activer l'environnement virtuel (Windows: .venv\Scripts\activate | Linux/Mac: source .venv/bin/activate)
pip install -e ".[dev]"
cp .env.example .env     # Renseigner GEMINI_API_KEY et TAVILY_API_KEY
uvicorn app.main:app --reload --port 8000
```
- API Docs Swagger : `http://127.0.0.1:8000/docs`

#### 2. Frontend (React + Vite)
```bash
cd equipe_frontend/parcours-ai-frontend
npm install
cp .env.example .env     # Configurer les clés Supabase si nécessaire
npm run dev
```
- Application Web : `http://localhost:5173/`

---

##  Structure du Projet

```text
├── backend/                  # API FastAPI, moteur de matching & services IA
│   ├── app/
│   │   ├── data/             # Catalogue national (530 filières & fiches métiers)
│   │   ├── routers/          # Endpoints API (/chat, /search, /feedbacks, etc.)
│   │   └── services/         # Orchestrateur, RAG, Gemini & Matching déterministe
├── equipe_frontend/          # Interface utilisateur React 19 & Tailwind CSS
│   └── parcours-ai-frontend/ # Application cliente Vite + TS
├── start_project.bat         # Script de démarrage rapide Windows
└── supabase_schema.sql       # Schéma de base de données PostgreSQL
```

---

## 👥 Équipe & Contexte
Projet conçu et réalisé pour le **Challenge Ignite Your Future** par l'équipe **PARCOURS-AI**.
