# InnoVest

InnoVest is a full-stack startup ecosystem platform built with Django and React. The project combines investor, startup, community, and operational workflows into a single application, including company management, user authentication, KYC verification, payments, event handling, and communication features.

## Overview

This repository contains the backend API and frontend client for a startup-focused platform. The backend is built with Django + Django REST Framework and exposes a broad set of REST endpoints for company and user operations. The frontend is a React application using Material UI and charting libraries for dashboards and management interfaces.

The project includes modules for:

- User authentication and authorization
- Company onboarding and company control
- Investment and fundraising workflow support
- KYC submission and verification
- Payments and gateway integration
- Email and notification systems
- Community and messaging services
- Event management
- ML-based startup analysis and risk evaluation
- Dashboard and reporting screens

## Tech Stack

### Backend
- Python
- Django 5.x
- Django REST Framework
- JWT authentication
- SQLite for local development
- CORS support for frontend integration

### Frontend
- React 18
- Material UI
- React Router
- Chart.js / Recharts
- Axios for API calls

### Additional tools
- Firebase integration
- SSLCommerz payment integration
- ML model support with scikit-learn / joblib
- Email delivery via SMTP and Resend

## Project Structure

```text
InnoVest/
├── Innovest/                 # Django project settings and URL routing
├── authentication/           # User auth and custom user model
├── backend/                  # Core backend logic and APIs
├── companies/                # Company-related endpoints/models
├── company_control/          # Company operations and control logic
├── company_permission/       # Company permission management
├── company_addUser/          # Add user to company workflow
├── contact/                  # Contact forms and messaging
├── payments/                 # Payment integration and invoice/payment routes
├── events/                   # Event management
├── chat/                     # Chat/community messaging
├── community_backend/        # Community features
├── emails/                  # Email-related logic
├── mailer/                  # Mailer utilities
├── kyc/                     # KYC data models/endpoints
├── kyc_control/             # KYC control workflow
├── my_companies/            # Company portfolio / user-company relations
├── my_companies_trackprogress/
├── my_companies_permission/
├── settings/                # App settings and configuration
├── user_control/            # User account management
├── ml_api/                  # Machine learning API endpoints
├── frontend/                # React frontend app
├── email-frontend/          # Secondary email frontend app
├── media/                   # Uploaded files/media
├── db.sqlite3               # SQLite database (local dev)
├── manage.py                # Django entry point
├── requirements.txt         # Python dependencies
├── package.json             # Root Node dependencies
├── manual_testing_dashboard.html
├── edge_automation_tests/  # Automated testing utilities
├── test_model_status.py     # ML or model utility checks
├── test_prediction.py       # Prediction utilities/tests
└── README.md
```

## Main Features

### Authentication and access control
- Custom user model through `authentication`
- JWT-based API authentication
- Email-based login backend support
- Role/permission flows for company users

### Company and startup operations
- Company onboarding and management
- Permission and assignment workflows
- Activity and progress tracking
- Startup-related data and dashboards

### KYC and compliance
- KYC submission flow
- Document storage and related media handling
- Verification and control endpoints

### Payments and financial workflows
- Payment routes and gateway integration
- SSLCommerz setup in the Django settings
- Frontend callback URLs configured for local development

### Community and communication
- Chat endpoints
- Community backend modules
- Contact form integration
- Email notification features

### Event management and reporting
- Event models, endpoints, and related resources
- Reporting and dashboard views

### AI / ML layer
- Model handling and prediction endpoints exist under `ml_api`
- Training data files and model artifacts such as `model.joblib`, `Startup_Dataset.csv`, and `HateSpeech_Dataset.csv` are present

## Setup and Installation

### 1. Create a virtual environment

```bash
python -m venv .venv
```

On Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

### 2. Install Python dependencies

```bash
pip install -r requirements.txt
```

### 3. Apply database migrations

```bash
python manage.py migrate
```

### 4. Create a Django admin user (optional but recommended)

```bash
python manage.py createsuperuser
```

### 5. Start the backend server

```bash
python manage.py runserver
```

The backend will run on:

```text
http://localhost:8000
```

### 6. Start the frontend

```bash
cd frontend
npm install
npm start
```

The frontend is expected to run on:

```text
http://localhost:3000
```

## Configuration Notes

The project is currently configured for local development and uses:

- SQLite database at the project root
- Django `DEBUG = True`
- Local URLs for frontend and backend communication
- SMTP email configuration for Gmail
- SSLCommerz sandbox mode enabled

Important: for production use, you should move sensitive values such as:

- `SECRET_KEY`
- email credentials
- payment credentials
- allowed hosts

into environment variables or a secure configuration system.

## Running the Project

In a typical local workflow:

1. Activate the Python environment
2. Run the Django backend
3. Open the frontend app in another terminal
4. Use the app via `http://localhost:3000`

## Notable Files

- `manage.py`: Django project entry point
- `Innovest/settings.py`: project configuration, installed apps, DB config, email config, JWT config
- `Innovest/urls.py`: API route setup
- `frontend/package.json`: React app dependencies and scripts
- `requirements.txt`: Python backend dependencies
- `manual_testing_dashboard.html`: manual testing dashboard file

## Development Notes

This repository appears to be a working, multi-module platform in active development. Some directories and files look like supporting utilities, manual tests, and experiment code rather than production core modules. The main application structure is centered around the Django project and the React frontend.

## Suggested Next Steps

- Move secrets into `.env` files
- Split development and production settings
- Add automated tests for key APIs
- Document the API endpoints more explicitly
- Review and clean legacy experimental files
- Standardize frontend and backend environment configuration

## License

This project does not currently declare a license in the repository root. If this project is intended for public or commercial use, add an appropriate license file before distribution.
