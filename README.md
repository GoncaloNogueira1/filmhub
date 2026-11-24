# FilmHub

Movie catalogue and recommendation web app. Users can browse and search films, rate them, keep a watchlist and get recommendations based on their ratings.

Developed for the Software Development Automation course (MSc in Informatics Engineering, University of Coimbra). The course compared two ways of building the same application: a team version developed manually, and this version, developed individually with an LLM from a sequence of prompts. The prompts are in [`llm/prompts`](llm/prompts).

## Stack

- **Backend:** Django, Django REST Framework, JWT authentication, PostgreSQL
- **Frontend:** React (Vite)
- **Infrastructure:** Docker, Docker Compose, GitHub Actions, GitHub Container Registry, Render

## Features

- User registration and JWT login
- Movie catalogue and search
- Ratings
- Personalised recommendations
- Watchlist

## CI/CD

The pipeline in [`.github/workflows/ci-cd.yml`](.github/workflows/ci-cd.yml) runs on every push and pull request to `main` and `develop`:

1. **Backend:** Pylint, Bandit, database migrations and pytest with coverage against a PostgreSQL service container
2. **Frontend:** ESLint, tests and production build
3. **Docker:** Compose validation and image builds for backend and frontend
4. **Release** (`main` only): images pushed to GitHub Container Registry and deployed to Render

## Running locally

```bash
git clone https://github.com/GoncaloNogueira1/filmhub.git
cd filmhub
docker compose up --build
```
