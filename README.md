# 💤 Sleep Tracker for macOS
Tracks your nightly sleep if you use your Mac right before bed and soon after waking up

It reads your Mac’s power logs to detect **nightly sleep durations** and records them to a CSV file.  
It’s built with Python and packaged as an Automator `.app` for easy sharing — just double-click to run.

## ✨ Features
- **Nightly window filtering** — only tracks sleep sessions between a start and end time (default: 23:00 → 13:00 next day).
- **Minimum duration rule** — ignores short naps; only counts segments ≥ 4 hours.
- **Multiple segments per night** — sums qualifying segments in the same window (e.g., if you wake up in the middle of the night).
- **CSV logging** — appends results to `sleepDuras.csv` on your Desktop.
- **Duplicate protection** — won’t log the same date twice.
- **Works offline** — uses built-in `pmset` logs (about 7 days history available).

## 🛠 Requirements
- macOS with `/usr/bin/python3` available (macOS 12+ ships with this).
- Access permission to read system power logs (`pmset`) and write to your Desktop.

## 📥 Installation
1. Download the latest `Sleep Tracker.app` from the [Releases](../../releases) page.
2. Move it to your preferred location (e.g., `Applications` or Desktop).
3. On first run, right-click → **Open** → confirm the security prompt.
4. Grant permissions if macOS asks for **Desktop folder access**.

## ▶️ Usage
1. **Double-click** the app to run it.
2. It will create `sleepDuras.csv` on your Desktop as the result.
