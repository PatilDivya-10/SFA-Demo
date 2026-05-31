# Smart Fashion Advisor

Skin tone detection, outfit recommendations, and fashion chatbot (Flask + MediaPipe).

## Railway deploy

1. Push this repo to GitHub (must include `data/styles.csv` and `data/images.csv`).
2. [Railway](https://railway.app) → **New Project** → **Deploy from GitHub repo**.
3. **Variables** (optional but recommended):
   - `FLASK_SECRET_KEY` — long random string (sessions)
   - `GEMINI_API_KEY` — [Google AI Studio](https://aistudio.google.com/apikey) (chatbot; works without it)
4. Generate a **public domain** in Railway networking settings.
5. First deploy may take 2–3 minutes. Check `https://YOUR-APP.up.railway.app/health` → `"catalog_loaded": true`.

Railway runs: `gunicorn app:app` (see `Procfile` / `railway.json`).

## Local run

```bash
pip install -r requirements.txt
python app.py
```

Open http://127.0.0.1:5000

## Project files

| Path | Purpose |
|------|---------|
| `app.py` | Backend |
| `templates/index.html` | Frontend |
| `data/styles.csv` | Product catalog |
| `data/images.csv` | Image URLs |
| `requirements.txt` | Python deps |
| `Procfile` | Railway start command |
| `railway.json` | Railway config |
| `runtime.txt` | Python 3.11 |
