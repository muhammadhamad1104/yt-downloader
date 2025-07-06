# yt-downloader

A powerful YouTube downloader built using Python and [yt-dlp](https://github.com/yt-dlp/yt-dlp), with support for high-quality video/audio downloads and bundled binaries for seamless offline usage.

---

## 🔧 First Time Setup

Make sure to create a virtual environment:

# Windows
python -m venv .venv
.venv\Scripts\activate

# macOS/Linux
python3 -m venv .venv
source .venv/bin/activate
Install dependencies:

pip install -r requirements.txt
📦 Included Binaries
The project includes the following pre-bundled binaries:


bin/
├── yt-dlp.exe
├── ffmpeg-master-latest-win64-gpl/bin/ffmpeg.exe
└── aria2-1.37.0-win-64bit-build1/aria2c.exe
These are included during the build to avoid requiring users to download them separately.

🚀 Build Instructions
🪟 Windows
Use PyInstaller to bundle everything into one .exe:

pyinstaller --noconfirm --onefile --windowed ^
  --add-data "bin;bin" ^
  --add-data "assets;assets" ^
  --add-data "history;history" ^
  --icon=assets/icon.ico ^
  --name yt-downloader yt-downloader.py
Make sure you're in a virtual environment, and that yt-dlp.exe, ffmpeg.exe, and aria2c.exe are present in the bin/ directory as shown.

🍎 macOS / 🐧 Linux
Install pyinstaller and use:

pyinstaller --noconfirm --onefile --windowed \
  --add-data "bin:bin" \
  --add-data "assets:assets" \
  --add-data "history:history" \
  --icon=assets/icon.ico \
  --name yt-downloader yt-downloader.py
Note: You’ll need macOS/Linux versions of:

yt-dlp (you can use the .pyz version or install via pip)

ffmpeg

aria2c

Place them in bin/ as with the Windows version.

📁 Directory Structure

yt-downloader/
├── yt-downloader.py
├── assets/
├── bin/
│   ├── yt-dlp.exe
│   ├── ffmpeg.exe
│   └── aria2c.exe
├── history/
├── .venv/
├── dist/
├── build/
├── README.md
└── requirements.txt
💡 Notes
All downloads and operations are handled by yt-dlp in the background.

This GUI supports advanced download options including playlists, audio-only, and subtitle downloads.
