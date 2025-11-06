# Vlad's Blog

A full-featured blog website built with Flask, featuring user authentication, admin controls, and comment functionality.

## Features

- User registration and authentication
- Admin-only post creation and editing
- Rich text editor for blog posts (CKEditor)
- Comment system with Gravatar integration
- Responsive design with Bootstrap
- SQLite database (with PostgreSQL support for production)

## Setup Instructions

### Prerequisites

- Python 3.10 or higher
- pip (Python package installer)

### Installation

1. Clone the repository:
```bash
git clone <your-repository-url>
cd BlogWeb
```

2. Create a virtual environment:
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Set up environment variables:
   
   The project includes a `.env` file for local development. For production:
   - Generate a secure secret key: `python -c "import secrets; print(secrets.token_hex(16))"`
   - Update `.env` with your production values
   - **IMPORTANT:** Never commit `.env` to version control (it's already in `.gitignore`)

5. Run the application:
```bash
python main.py
```

The application will be available at `http://localhost:5001`

## Database

The application automatically creates the database tables on first run. The first user to register will be the admin (user ID 1).

## Deployment

This application is configured for deployment on platforms like Heroku or Render using the included `Procfile`.

For production deployment:
1. Set the `FLASK_KEY` environment variable to a secure random string
2. Set the `DB_URI` to your PostgreSQL database connection string
3. Deploy using the platform's standard deployment process

## Admin Features

The first registered user (ID 1) has admin privileges and can:
- Create new blog posts
- Edit existing posts
- Delete posts

## Technologies Used

- Flask 2.3.2
- Flask-Login for authentication
- Flask-SQLAlchemy for database management
- Flask-WTF for forms
- Flask-CKEditor for rich text editing
- Bootstrap 5 for styling
- Gravatar for user avatars
