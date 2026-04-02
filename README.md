# Skills App Pro - Flask Application

## Overview

A comprehensive skills tracking and job posting application built with Flask. The app allows users to:
- Create profiles with their skills and experience
- Browse and apply for jobs  
- Connect with other professionals
- Manage their professional portfolio

## Features

### User Management
- User registration and authentication
- Profile management with bio, skills, and resume
- "Remember Me" functionality for persistent login
- Admin dashboard for user management

### Skills Tracking  
- Add and manage skills with proficiency levels
- Track skill development over time
- Visualize skill progress

### Job Listings
- Post and browse job opportunities  
- Save favorite job postings
- Apply directly through the platform

## Installation

### Prerequisites
- Python 3.8+
- PostgreSQL  
- pip

### Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/ahmedsamir46/Big-Skills.git
   cd Skill_app_flask
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Set up environment variables:
   Create a `.env` file with:
   ```
   SECRET_KEY=your_secret_key_here
   DATABASE_URL=postgresql://username:password@localhost/dbname
   ```

5. Initialize the database:
   ```bash
   flask db init
   flask db migrate
   flask db upgrade
   ```

6. Run the application:
   ```bash
   flask run
   ```

## Configuration

| Variable | Description | Default |
|----------|-------------|---------|  
| `SECRET_KEY` | Flask secret key | Required |
| `DATABASE_URL` | Database connection URL | Required |
| `FLASK_ENV` | Application environment | `production` |
| `FLASK_DEBUG` | Debug mode | `0` |

## API Endpoints

### Authentication
- `POST /auth/register` - User registration  
- `POST /auth/login` - User login
- `GET /auth/logout` - User logout

### User Profiles
- `GET /user/<username>` - Get user profile  
- `PUT /user/<username>` - Update profile

### Skills
- `POST /skills` - Add new skill
- `GET /skills` - List all skills  
- `DELETE /skills/<id>` - Remove skill

## Deployment

### Heroku
```bash
heroku config:set FLASK_ENV=production
heroku config:set SECRET_KEY=your_secret_key
git push heroku main
heroku run flask db upgrade
```

### Docker
```bash
docker build -t skills-app .
docker run -d -p 5000:5000 --env-file .env skills-app
```

## Contributing

1. Fork the repository  
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to the branch (`git push origin feature/fooBar`)  
5. Create a new Pull Request

[License: GNU General Public License v3.0](LICENSE)
