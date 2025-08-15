# 💤 Sleep Tracker for macOS
Sleep Duration Tracker for people who use Mac before going to sleep and open the Mac soon after waking up.

A small macOS app that reads your Mac’s power logs to detect **nightly sleep durations** and records them to a CSV file.  
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
1. Download the latest `Sleep Tracker.app` from the [Releases](../../releases) page (or receive it via AirDrop/zip).
2. Move it to your preferred location (e.g., `Applications` or Desktop).
3. On first run, right-click → **Open** → confirm the security prompt.
4. Grant permissions if macOS asks for **Desktop folder access**.

## ▶️ Usage
1. **Double-click** the app to run it.
2. It will:
   - Parse the last 7 days of `pmset` logs.
   - Find all `Display is turned off → on` pairs inside your nightly window.
   - Apply the 4-hour minimum rule and sum multiple segments per date.
   - Append new results to `sleepDuras.csv` on your Desktop.
