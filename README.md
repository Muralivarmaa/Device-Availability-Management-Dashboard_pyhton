Windows (Command Prompt)

cd "C:\path\to\your\project" python -m venv venv venv\Scripts\activate pip install -r requirements.txt python app.py

for Windows (PowerShell)----

cd "C:\path\to\your\project" python -m venv venv

allow activation for this session (no system-wide change)
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process -Force .\venv\Scripts\Activate.ps1 pip install -r requirements.txt python app.py

for macOS / Linux---

cd /path/to/your/project python3 -m venv venv source venv/bin/activate pip install -r requirements.txt python app.py

Open the dashboard in your browser
When the server starts you will see something like:

Running on http://127.0.0.1:50***
Open:

http://127.0.0.1:5000 ((If you want to access from another device on the same LAN, find your machine IP, e.g. 192.168.1.10, and open http://192.168.6.4:5000. The port stays 5000 unless you change it in app.py.))

Stop the server Press Ctrl + C in the terminal where the server is running.
Notes & troubleshooting

ModuleNotFoundError: No module named 'flask' → you must activate the venv before pip install -r requirements.txt (or install Flask globally with pip install flask).

If PowerShell blocks activation, the Set-ExecutionPolicy -Scope Process -ExecutionPolicy RemoteSigned -Force command (above) lets you run the activation script for the current session.

If the page shows Not Found or blank, ensure you ran python app.py from the project root (where app.py is).

To persist state between restarts, replace in-memory device list with a database (SQLite) — ask me if you want that.

Files included

app.py — Flask app (server + routes)

requirements.txt — dependencies (includes Flask)

templates/ — index.html

static/ — CSS + JS assets

above ive uploaded the zip file to extract all the files . (check it out).
