# DevAtlas – The Developer Command & Learning Hub

> A clean, modern, and visually engaging web hub that provides quick command references and learning guides for developers.

---

## What is DevAtlas?

DevAtlas is a **developer reference platform** built with Flask. It gives developers instant access to the essential commands and patterns they use every day — organized, readable, and always one click away.

No databases. No JavaScript frameworks. No fluff. Just clean Flask and HTML, ready to containerize.

---

## Features

- 🐧 **Linux Commands** — 20 essential terminal commands with examples
- 🌿 **Git Commands** — 20 version control commands from init to cherry-pick
- 🐳 **Docker Commands** — 20 container and Compose commands for dev to prod
- 🐍 **Python Tips** — 20 Pythonic patterns, builtins, and modern features
- ⚗️ **Flask Tips** — 20 production patterns for clean Flask applications
- 🎨 **Professional dark UI** — sticky nav, card grids, code blocks, hover effects
- 📱 **Fully responsive** — works on mobile, tablet, and desktop

---

## Project Structure

```
devatlas/
├── templates/
│   ├── index.html      # Homepage — navigation hub
│   ├── linux.html      # Linux Commands page
│   ├── git.html        # Git Commands page
│   ├── docker.html     # Docker Commands page
│   ├── python.html     # Python Tips page
│   └── flask.html      # Flask Tips page
├── static/
│   └── style.css       # All styles — dark theme, cards, animations
├── app.py              # Flask app — all routes and data
├── requirements.txt    # Python dependencies
└── README.md           # This file
```

---

## How to Install

**1. Clone or download the project**

```bash
git clone https://github.com/yourname/devatlas.git
cd devatlas
```

**2. (Optional) Create a virtual environment**

```bash
python -m venv venv
source venv/bin/activate        # Linux / macOS
venv\Scripts\activate           # Windows
```

**3. Install dependencies**

```bash
pip install -r requirements.txt
```

---

## Run the Application

```bash
python app.py
```

Then open your browser and go to:

```
http://localhost:5000
```

---

## Tech Stack

| Layer     | Technology     |
|-----------|---------------|
| Backend   | Python Flask   |
| Frontend  | HTML + CSS     |
| Fonts     | Space Mono, DM Sans (Google Fonts) |
| Storage   | None — all data is in `app.py` |

---

## Docker (Coming Soon)

This project is structured to be easily containerized. A `Dockerfile` will be added in the next phase.

```dockerfile
# Example Dockerfile (future phase)
FROM python:3.11-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
EXPOSE 5000
CMD ["python", "app.py"]
```

---

## License

MIT — free to use, modify, and learn from.
