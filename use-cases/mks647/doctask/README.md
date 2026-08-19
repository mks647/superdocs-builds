# DocTask

## Open-Source Governance Pack Generator

DocTask is a full-stack web application that helps users create projects and automatically generate a complete set of open-source governance documents.

Instead of manually creating and maintaining common repository governance files, users can provide project information through a web interface and generate a structured governance pack that can be reviewed, downloaded individually, or exported as a ZIP archive.

## What It Does

DocTask provides a simple workflow for generating governance documentation for an open-source project:

1. Create a governance project.
2. Enter and validate project information.
3. Generate the governance document set.
4. View the generated documents.
5. Download individual Markdown files.
6. Download the complete governance pack as a ZIP file.

## Key Features

* Create governance projects
* Store projects in a database
* Validate project information
* Prevent duplicate project names
* Generate governance documents
* View generated documents
* Download individual Markdown documents
* Download the complete governance pack as a ZIP file
* Delete projects with confirmation
* Responsive web interface

## Generated Governance Documents

For each project, DocTask can generate:

* `CODE_OF_CONDUCT.md`
* `CONTRIBUTING.md`
* `SECURITY.md`
* `MAINTAINERS.md`
* `CLA.md`
* `RELEASE_POLICY.md`

These documents provide a reusable governance baseline for open-source repositories.

## Why DocTask?

Open-source projects frequently need several governance files before they can be shared publicly.

Creating these documents manually is repetitive and can lead to:

* Missing governance documents
* Inconsistent project information
* Repeated manual editing
* Difficult-to-maintain documentation packages

DocTask addresses this by collecting project information once and using it to generate a consistent governance pack.

## Technology Stack

### Frontend

* React
* Axios
* CSS

### Backend

* Python
* FastAPI
* SQLAlchemy
* Pydantic

### Database

* SQLite

### Document Generation

* Python-based document generation
* Markdown output
* ZIP archive export

## Architecture

```text
                         User
                           │
                           ▼
                   React Frontend
                           │
                         Axios
                           │
                           ▼
                    FastAPI Backend
                           │
                  ┌────────┴────────┐
                  ▼                 ▼
              SQLite DB     Document Generator
                                    │
                                    ▼
                           Governance Documents
                                    │
                         ┌──────────┴──────────┐
                         ▼                     ▼
                     Markdown                 ZIP
```

## Project Structure

```text
doctask/
│
├── backend/
│   ├── main.py
│   ├── database.py
│   ├── models.py
│   ├── schemas.py
│   ├── document_generator.py
│   └── templates/
│
├── frontend/
│   └── src/
│
└── README.md
```

## How to Run

### Prerequisites

Make sure the following are installed:

* Python 3.x
* Node.js and npm
* Git

### 1. Clone the Project

```bash
git clone <repository-url>
cd doctask
```

### 2. Start the Backend

```bash
cd backend

python -m venv venv
```

Activate the virtual environment.

#### Windows

```bash
venv\Scripts\activate
```

Install the Python dependencies:

```bash
pip install -r requirements.txt
```

Start the FastAPI application:

```bash
uvicorn main:app --reload
```

The backend will normally be available at:

```text
http://127.0.0.1:8000
```

FastAPI's interactive API documentation:

```text
http://127.0.0.1:8000/docs
```

### 3. Start the Frontend

Open another terminal:

```bash
cd frontend
npm install
npm run dev
```

The frontend will normally be available at:

```text
http://localhost:5173
```

## Environment Variables

If environment variables are required for a local configuration, create a `.env` file.

Use placeholders only in documentation:

```text
SUPERDOCS_API_KEY=your-key-here
```

Never commit real API keys, tokens, passwords, or other secrets.

If a `.env.example` file is provided, use it as the configuration template.

## SuperDocs Features Used

DocTask is submitted as a SuperDocs community **use case**.

The project demonstrates a document-generation workflow that fits the SuperDocs ecosystem's focus on document workflows and practical applications.

### Integration Surface

The project uses the application's document workflow to create and package governance documentation.

**SuperDocs feature used:** `[API / MCP / Export / other actual integration — update this section to match the final implementation]`

> Before submission, this section must contain only the SuperDocs capability that is actually implemented and demonstrated by this project. Do not claim an integration that is not present in the final code.

## Demo

A short demonstration video will show the complete workflow:

1. Open DocTask.
2. Create a governance project.
3. Enter project information.
4. Generate the governance documents.
5. View the generated documents.
6. Download the governance pack as a ZIP file.

**Demo video:** `[Add demo video link]`

**Live deployment:** `[Add live deployment link if available]`

## Example Use Case

A developer creates a new open-source repository and needs a basic governance package.

Instead of manually creating six Markdown files, the developer can create a project in DocTask, enter the required project information, generate the governance pack, review the files, and download the complete package as a ZIP archive.

The generated files can then be added to the target repository.

## API

The backend is powered by FastAPI and exposes the application's project and document-generation workflow through HTTP endpoints.

Health check:

```text
GET /api/health
```

Project operations include endpoints for creating and retrieving governance projects.

The interactive API documentation is available when the backend is running:

```text
http://127.0.0.1:8000/docs
```

## Security

DocTask should be configured carefully when used with real project information.

* Never commit API keys.
* Never commit passwords or authentication tokens.
* Keep local secrets in environment variables.
* Use placeholder values in `.env.example` and documentation.
* Do not upload sensitive project information to a public repository.
* Production deployments should use appropriate authentication and access controls.

## Future Improvements

Potential future enhancements include:

* PDF export
* DOCX export
* Additional governance templates
* Project versioning
* User authentication
* Role-based access control
* PostgreSQL support
* Cloud deployment
* Automated tests
* CI/CD integration
* AI-assisted document refinement

## Author

**Mukul Choudhary**

GitHub: `@mks647`

## License

This project is contributed to the SuperDocs Builds repository under its MIT-licensed contribution model.
