# Portfolio

A full-stack portfolio project scaffolded on Emergent.

## Tech Stack

- **Frontend**: React (CRA + CRACO), Tailwind CSS, shadcn/ui components
- **Backend**: FastAPI (Python)
- **Database**: MongoDB
- **Package Managers**: Yarn (frontend), pip (backend)

## Project Structure

```
.
├── backend/         # FastAPI application
│   ├── server.py
│   ├── requirements.txt
│   └── .env         # (not committed) MONGO_URL, DB_NAME, CORS_ORIGINS
├── frontend/        # React application
│   ├── src/
│   ├── package.json
│   └── .env         # (not committed) REACT_APP_BACKEND_URL
└── tests/
```

## Environment Variables

Create the following `.env` files (never commit real values):

**`backend/.env`**
```
MONGO_URL="mongodb://localhost:27017"
DB_NAME="portfolio_db"
CORS_ORIGINS="*"
```

**`frontend/.env`**
```
REACT_APP_BACKEND_URL=http://localhost:8001
WDS_SOCKET_PORT=443
```

## Local Setup

### Backend
```bash
cd backend
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
uvicorn server:app --host 0.0.0.0 --port 8001 --reload
```

### Frontend
```bash
cd frontend
yarn install
yarn start
```

Ensure MongoDB is running locally on port `27017` (or update `MONGO_URL`).

## API Convention

All backend routes are prefixed with `/api` and reached via `REACT_APP_BACKEND_URL` from the frontend.

## License

MIT
