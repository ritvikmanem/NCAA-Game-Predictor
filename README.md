# NCAA Basketball Prediction Model

## Overview
This project predicts NCAA basketball game outcomes using machine learning. The model is trained on the current season’s data and can predict match results, including those in the March Madness tournament.

## Features
- **Web Scraping**: Automatically collects and updates NCAA basketball game data.
- **Database Storage**: Uses PostgreSQL to store historical game records.
- **Machine Learning Model**: Predicts game outcomes based on team performance.
- **FastAPI Backend**: Exposes prediction API endpoints.
- **React.js Frontend**: Interactive web interface for predictions.
- **Deployment**: Hosted using Render (backend & database) and Vercel (frontend).

## Tech Stack

### Backend
- FastAPI - High-performance API framework.
- PostgreSQL - Relational database for storing NCAA game data.
- SQLAlchemy - ORM for database interactions.
- Scikit-learn - Machine learning library for model training.

### Frontend
- React.js - JavaScript library for UI development.
- Tailwind CSS - Utility-first CSS framework for styling.
- Axios - HTTP client for API communication.

### Deployment
- Vercel - Hosts the frontend.
- Render - Hosts the backend and PostgreSQL database.

## Project Structure
```
backend/
  app/
    __init__.py
    main.py         # FastAPI app
    models.py       # SQLAlchemy models
    predict.py      # ML model logic
    database.py     # Database connection
  requirements.txt  # Backend dependencies

frontend/
  src/
    components/
    App.js          # Main React component
    index.js        # Entry point
  package.json      # Frontend dependencies

database/
  schema.sql        # PostgreSQL schema

README.md
.gitignore
```

## Setup Instructions

### 1. Clone the Repository
```sh
git clone https://github.com/yourusername/ncaa-basketball-prediction.git
cd ncaa-basketball-prediction
```

### 2. Backend Setup (FastAPI & PostgreSQL)
```sh
cd backend
pip install -r requirements.txt
```
- Set up PostgreSQL database:
  - Create a database `ncaa_db`.
  - Run `schema.sql` to create tables.
- Start the backend:
```sh
uvicorn app.main:app --reload
```
- API runs at `http://127.0.0.1:8000`

### 3. Frontend Setup (React.js)
```sh
cd frontend
npm install
npm start
```
- App runs at `http://localhost:3000`

## API Endpoints
| Method | Endpoint | Description |
|--------|---------|-------------|
| GET | `/predict/?team1=UNC&team2=Duke` | Predicts game winner |
| GET | `/teams/` | Returns available teams |
| GET | `/games/` | Returns past game results |

## Machine Learning Model
The model is built using Scikit-learn and trained on the current season’s data using:
- Team win/loss records
- Point differentials
- Home/away performance
- Head-to-head results

## Deployment
- **Frontend:** Vercel (`npm run build` → Deploy to Vercel)
- **Backend & Database:** Render (`uvicorn app.main:app` hosted on Render)

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Contributors
- [Your Name](https://github.com/yourusername)
