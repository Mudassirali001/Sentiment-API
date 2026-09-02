# Week 7 Sentiment API

A small FastAPI service that demonstrates GET routes, path and query parameters, Pydantic request validation, and a scikit-learn sentiment classifier.

## Requirements

- Python 3.10 or newer

## Setup

Create and activate a virtual environment, then install the dependencies:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

## Run the API

From this directory, start the development server:

```powershell
uvicorn ai_api:app --reload
```

The API is available at `http://127.0.0.1:8000`. Interactive OpenAPI documentation is available at `/docs`.

## Endpoints

| Method | Path | Description |
| --- | --- | --- |
| `GET` | `/` | Health and project message |
| `GET` | `/user/{id}` | Returns the supplied integer user ID |
| `GET` | `/search?name=...` | Returns the supplied name |
| `POST` | `/predict` | Predicts sentiment for a text review |

Example prediction request:

```powershell
Invoke-RestMethod -Method Post `
  -Uri http://127.0.0.1:8000/predict `
  -ContentType 'application/json' `
  -Body '{"text":"I love this movie"}'
```

Example response:

```json
{
  "text": "I love this movie",
  "prediction": "Positive"
}
```

The demonstration model is trained from four example reviews when `model.py` is imported. It is intended for learning and is not production-grade sentiment analysis.

## Test

Run the test suite with:

```powershell

pytest
```
## author
Mudassir ali
