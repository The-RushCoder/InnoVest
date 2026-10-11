# InnoVest

InnoVest is a startup crowdfunding web application built with a React frontend and a Django REST Framework backend. The project brings together startup and company information, fundraising details, user accounts, investment-related workflows, and supporting services in one web application.

## Overview

The application is organized as a full-stack project:

- **Frontend:** React 18, React Router, Material UI, Axios, Firebase, and charting components.
- **Backend:** Django and Django REST Framework.
- **Authentication:** Django authentication with JWT support through Simple JWT.
- **Database:** SQLite is configured as the default database in the current Django settings.
- **Supporting modules:** Payments, company and user management, permissions, events, email services, chat, community features, KYC, and an ML API.

## Key Features

- User authentication and account-related workflows
- Startup/company profiles and company management
- Business plan and fundraising-term APIs
- Investment and transaction-related workflows
- Role and permission management
- KYC submission and related controls
- Payment integration configured for sandbox use
- Events, contact, email, chat, and community modules
- React-based frontend connected to backend APIs
- Machine-learning API module

Feature availability depends on the relevant module configuration and local environment. This repository is a development project and should not be treated as a production deployment without further configuration and security review.

## Technology Stack

| Layer | Technologies |
|---|---|
| Frontend | React, JavaScript, React Router, Material UI, Axios, Firebase |
| Backend | Python, Django, Django REST Framework |
| Authentication | Simple JWT |
| Database | SQLite by default |
| Data and ML | Pandas, NumPy, scikit-learn, SciPy, Joblib |
| Integrations | Payment, email, and API integrations |
| Version control | Git, GitHub |

## Repository Structure

```text
InnoVest/
├── Innovest/                 # Django project configuration and URL routing
├── authentication/           # Authentication-related application
├── backend/                  # Core backend views and APIs
├── companies/                # Company-related functionality
├── payments/                 # Payment-related functionality
├── ml_api/                   # Machine-learning API endpoints
├── events/                   # Event-related functionality
├── chat/                     # Chat functionality
├── community_backend/        # Community functionality
├── kyc/                      # KYC-related functionality
├── frontend/                 # React frontend
├── media/                    # User and application media files
├── manage.py                 # Django management command entry point
├── requirements.txt          # Python dependencies
└── README.md
```

Additional app directories handle permissions, user/company controls, email, settings, and company progress tracking.

## Requirements

Install the following before running the project:

- Python 3.10 or later
- Node.js and npm
- Git

## Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/The-RushCoder/InnoVest.git
cd InnoVest
```

### 2. Set up the backend

Create and activate a virtual environment.

**Windows PowerShell**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

**macOS/Linux**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install the Python dependencies and apply database migrations:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

The Django development server normally runs at `http://127.0.0.1:8000/`.

### 3. Set up the frontend

Open another terminal at the repository root:

```bash
cd frontend
npm install
npm start
```

The React development server normally runs at `http://localhost:3000/`.

If the frontend API base URL is configured in source code, update it to match the local backend URL before testing the application.

## API Overview

The backend exposes REST endpoints under `/api/`. The project URL configuration includes routes for areas such as:

- Authentication: `/api/auth/`
- Payments: `/api/payments/`
- Company and business-plan data
- Fundraising terms
- Events and contact
- User and company permissions
- Email and mailer services
- Chat and community
- KYC submission and management
- Machine-learning endpoints: `/api/ml/`

For the exact route names and request/response schemas, refer to `Innovest/urls.py` and the URL configuration inside each application.

## Configuration and Security

Before running the project, review `Innovest/settings.py` and the relevant integration modules. Configure your own development credentials for email and payment services, and keep secrets outside source control.

**Do not commit API keys, passwords, payment credentials, production data, or private user documents.** Use environment variables or a local, untracked configuration file for credentials. The current project configuration should receive a security review before any public or production deployment, including `SECRET_KEY`, `DEBUG`, `ALLOWED_HOSTS`, CORS settings, email settings, and payment settings.

The payment integration is configured for sandbox use in the current settings. Use test credentials for local development.

## Development Notes

- The backend uses Django migrations to manage database schema changes.
- API authentication is configured with JWT support through Django REST Framework Simple JWT.
- The frontend and backend run as separate development servers.
- Keep frontend API URLs, CORS configuration, and local service settings consistent when changing ports or environments.

## Current Scope

InnoVest is a project for demonstrating full-stack application development, API integration, database-backed workflows, and supporting services. Deployment steps, credentials, and environment-specific settings may need to be adapted for your own machine.

## Author

**Mohin Khan**

GitHub: [The-RushCoder](https://github.com/The-RushCoder)
