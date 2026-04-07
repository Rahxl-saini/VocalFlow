# 🎙️ VocalFlow for Windows

A sleek and powerful **voice-to-text desktop application** for Windows that converts your speech into text in real-time, with optional AI-powered text enhancement.

Built using **Electron.js**, this app integrates **Deepgram** for fast and accurate speech recognition and **Groq** for intelligent grammar and text refinement.

---

## ✨ Key Features

* 🎤 **Real-time Speech-to-Text** using Deepgram (Nova-2 model)
* 🤖 **AI Text Enhancement** (grammar, clarity, spelling) via Groq LLM
* 📊 **API Status Dashboard** (Deepgram balance + Groq availability)
* 🧩 **System Tray Support** (run in background)
* ⌨️ **Global Hotkey**: `Alt + Shift + V` to start/stop recording
* 🌍 **Multi-language Support**:

  * English
  * Hindi
  * Spanish
  * French
  * German
  * Japanese
  * Chinese
* 📋 **One-click Copy to Clipboard**

---

## 🛠️ Tech Stack

* **Electron.js** – Cross-platform desktop framework
* **Deepgram API** – Real-time speech-to-text (WebSocket)
* **Groq API** – AI text enhancement (LLM)
* **HTML / CSS / JavaScript** – Lightweight frontend (no frameworks)

---

## 📁 Project Structure

```
vocalflow-windows/
├── config/
│   └── default.json
├── src/
│   ├── main/
│   │   ├── main.js
│   │   └── preload.js
│   └── renderer/
│       ├── index.html
│       ├── styles.css
│       ├── app.js
│       ├── assets/
│       │   └── tray-icon.png
│       └── services/
│           ├── audioCapture.js
│           ├── deepgram.js
│           └── groq.js
├── package.json
├── .gitignore
└── README.md
```

---

## ⚙️ Setup Guide

### 🔹 Prerequisites

Make sure you have:

* Node.js (v18 or above)
* Deepgram API Key (free credits available)
* Groq API Key (optional but recommended)

---

### 🚀 Installation Steps

1. **Clone the repository**

```bash
git clone https://github.com/Sanchit029/vocalflow.git
cd vocalflow
```

2. **Install dependencies**

```bash
npm install
```

3. **Configure API Keys**

Edit the file:

```
config/default.json
```

Add your keys:

```json
{
  "deepgram": {
    "apiKey": "YOUR_DEEPGRAM_KEY"
  },
  "groq": {
    "apiKey": "YOUR_GROQ_KEY"
  }
}
```

4. **Run the application**

```bash
npm start
```

---

## 🎯 How to Use

1. Launch the app using `npm start`
2. Check API status at the top (balance + connectivity)
3. Press **Alt + Shift + V** or click the mic button
4. Start speaking 🎙️
5. Watch real-time transcription appear instantly
6. Enable **AI Enhance** for improved text quality
7. Click **Copy** to save text to clipboard

---

## ⚙️ How It Works

1. **Audio Capture**

   * Uses Web Audio API
   * Converts Float32 audio → 16-bit PCM (16kHz)

2. **Speech Recognition (Deepgram)**

   * Streams audio via WebSocket
   * Receives real-time transcription

3. **AI Enhancement (Groq)**

   * Sends text to LLM (LLaMA model)
   * Improves grammar and clarity

4. **Status Monitoring**

   * Fetches Deepgram balance
   * Checks Groq API availability

---

## 🔄 macOS vs Windows Version

| Feature      | macOS (Original) | Windows (This App)      |
| ------------ | ---------------- | ----------------------- |
| Language     | Swift + SwiftUI  | Electron (JS)           |
| Audio Engine | AVAudioEngine    | Web Audio API           |
| Shortcut     | Native macOS     | Electron globalShortcut |
| Storage      | Keychain         | JSON config             |
| UI           | Native           | HTML/CSS                |

---

## ⚠️ Limitations

* 🔐 Credentials stored in JSON (not secure for production)
* ✍️ No direct text injection into other apps (clipboard only)
* 🌍 Limited language set (can be expanded easily)

---

## 🚀 Future Improvements

* Secure credential storage (OS keychain)
* Direct text injection into active apps
* More language support
* Better UI/UX polish
* Offline mode support (if feasible)

---

## 📄 License

MIT License

---

## 🙌 Credits

Inspired by the original macOS VocalFlow app by Vocallabs AI.

---

💡 *Built for productivity, speed, and simplicity.*
