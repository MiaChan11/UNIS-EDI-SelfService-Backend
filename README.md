
# UNIS EDI Self-Service Backend (Flask)

A Python Flask backend service for customer self-onboarding, supporting document uploads and label retrieval.

---

## Project Structure

```
UNIS-EDI-SelfService-Backend/
├── .github/
│   ├── workflows/
│   │   └── python-app.yml
│   └── ISSUE_TEMPLATE/
│       ├── bug_report.md
│       └── feature_request.md
├── app/
│   ├── __init__.py
│   ├── core/
│   │   ├── services/
│   │   │   ├── auth.py
│   │   │   ├── upload.py
│   │   │   └── search.py
│   │   └── models/
│   │       ├── user.py
│   │       └── document.py
│   ├── api/
│   │   ├── v1/
│   │   │   ├── auth.py
│   │   │   ├── upload.py
│   │   │   └── search.py
│   │   └── schemas.py
│   ├── storage/
│   │   ├── local_storage.py
│   │   └── s3_storage.py
│   ├── utils/
│   │   ├── auth.py
│   │   └── validation.py
│   └── config.py
├── tests/
│   ├── unit/
│   │   ├── test_services/
│   │   └── test_models/
│   └── integration/
│       ├── test_api/
│       └── conftest.py
├── migrations/
├── requirements/
│   ├── base.txt
│   ├── dev.txt
│   └── prod.txt
├── .env.example
├── .gitignore
├── LICENSE
└── README.md
```

---

## Quick Start

### Prerequisites
- Python 3.9+
- Git

### 1. Clone the repository
```bash
git clone https://github.com/MiaChan11/UNIS-EDI-SelfService-Backend.git
cd UNIS-EDI-SelfService-Backend
```

### 2. Set up the environment
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate    # Windows
pip install -r requirements/dev.txt
```

### 3. Configure environment variables
Copy `.env.example` to `.env` and modify:
```bash
cp .env.example .env
```
Edit `.env`:
```ini
FLASK_APP=app
FLASK_ENV=development
DATABASE_URL=sqlite:///app.db
SECRET_KEY=your-secret-key
```

### 4. Run the development server
```bash
flask run --port 5000
```
API Docs: `http://localhost:5000/api/docs`

---

## Developer Guide

### Database Migrations
```bash
flask db init
flask db migrate -m "Initial migration"
flask db upgrade
```

### Running Tests
```bash
pytest tests/
```

### Code Standards
- Branch naming: `feat/description`, `fix/description`
- Commit message format:
  ```bash
  git commit -m "feat(upload): add PDF support"
  git commit -m "fix(auth): resolve token expiration"
  ```

---

## API Documentation
- **Swagger UI**: `http://localhost:5000/api/docs`
- **Postman Collection**: See `docs/api_postman_collection.json`

---

## License
MIT License. See [LICENSE](./LICENSE).
```

---

### Key Files (Copy-Paste Ready)

#### `.env.example`
```ini
FLASK_APP=app
FLASK_ENV=development
DATABASE_URL=sqlite:///app.db
SECRET_KEY=change-this-to-a-random-string
UPLOAD_FOLDER=./uploads
```

#### `requirements/dev.txt`
```text
-r base.txt
pytest==7.4.0
pytest-cov==4.1.0
flask-debugtoolbar==0.13.1
```

#### `.gitignore`
```gitignore
# Python
__pycache__/
venv/
*.pyc

# Environment
.env

# Database
*.db
*.sqlite3

# IDE
.vscode/
.idea/
```

---

### Initial Setup Commands
```bash
git clone https://github.com/MiaChan11/UNIS-EDI-SelfService-Backend.git
cd UNIS-EDI-SelfService-Backend
python -m venv venv
source venv/bin/activate  # Linux/Mac
pip install -r requirements/dev.txt
flask run --port 5000
```

