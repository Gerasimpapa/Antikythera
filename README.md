# Antikythera Rings AD16

Antikythera Rings AD16 is a Python/Kivy application that displays planetary ring images inspired by the Antikythera mechanism. The rings rotate according to ecliptic longitude values calculated with Astronomy Engine for a selected UTC date and time.

## Project Structure

```text
Antikythera/
├── README.md
├── Rings/
│   ├── ring_moon.png
│   ├── ring_mercury.png
│   ├── ring_venus.png
│   ├── ring_sun.png
│   ├── ring_mars.png
│   ├── ring_jupiter.png
│   └── ring_saturn.png
└── Scripts/
    └── anti16.py
```

The script expects the ring images in `Rings/` relative to the project root. It can be launched from the project root or from another working directory because it resolves the image path from the script location.

## Dependencies

- Python 3
- Kivy
- python-dateutil
- Astronomy Engine Python package

If using the local Astronomy Engine source folder, install it in editable mode from the parent Antikythera source tree:

```bash
python -m pip install -e astronomy_local/astronomy_src/source/python
```

## Setup

From WSL bash:

```bash
cd "/mnt/g/My Drive/Projects/Antikythera"
python3 -m venv ~/.venvs/antikythera
source ~/.venvs/antikythera/bin/activate
python -m pip install --upgrade pip
python -m pip install kivy python-dateutil
```

If `astronomy_local` is outside this repository, install it using its actual path. For example:

```bash
python -m pip install -e "/mnt/g/.shortcut-targets-by-id/1s0x7g4ld_7KxrQ1erKAeKnZFomDEuX8e/Antikythera/astronomy_local/astronomy_src/source/python"
```

## Run

```bash
cd "/mnt/g/My Drive/Projects/Antikythera"
source ~/.venvs/antikythera/bin/activate
python Scripts/anti16.py
```

## Manual

The app opens with the current UTC date and time. The ring display updates whenever the selected date changes.

Controls:

- `UTC Date/Time`: enter a date manually in `YYYY-MM-DD HH:MM` format.
- Slider: move across roughly 100 years before or after the launch date.
- `Now`: return to the current UTC date and time.
- `-Day` / `+Day`: step backward or forward by one day.
- `-Month` / `+Month`: step backward or forward by one month.
- `-Year` / `+Year`: step backward or forward by one year.
- `-Decade` / `+Decade`: step backward or forward by ten years.

## GitHub Workflow

After changing files:

```bash
git status
git add README.md Scripts/anti16.py Rings/
git commit -m "Add AD16 script and ring assets"
git push
```

