# 🎙️ BEAST — Intelligent Virtual Assistant

> **An interactive, voice-controlled desktop assistant built with Python, Google Speech Recognition, and offline Text-to-Speech (TTS) synthesis.**

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![SpeechRecognition](https://img.shields.io/badge/SpeechRecognition-Google_API-red?style=for-the-badge)](https://pypi.org/project/SpeechRecognition/)
[![Pyttsx3](https://img.shields.io/badge/pyttsx3-Offline_TTS-emerald?style=for-the-badge)](https://pypi.org/project/pyttsx3/)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

---

## 📌 Overview

**BEAST** (*Behavioral Execution & Automated Speech Terminal*) is an extensible desktop virtual assistant developed in Python. It listens to user voice commands through a microphone, translates audio to text using speech recognition, identifies intent, executes desktop automation tasks, and provides natural conversational voice feedback using text-to-speech synthesis.

---

## ✨ Key Features

- **🎙️ Wake-Word Listening:** Continuously monitors ambient microphone input and activates upon hearing the wake-word **`"Beast"`**.
- **🗣️ Natural Voice Output:** Uses `pyttsx3` for fast, offline, and natural-sounding speech responses without requiring an active cloud connection.
- **🌐 Web & Workflow Automation:** Instantly launches system web browsers and navigates to frequently used developer platforms:
  - Google Search
  - YouTube
  - LinkedIn
  - Instagram & Facebook
- **⚙️ Modular Command Pipeline:** Clean intent-matching dispatcher that easily scales to handle custom desktop automation, system tasks, and external API requests.
- **🤖 LLM / Generative AI Ready:** Architected with integration hooks for Gemini / OpenAI models to answer complex open-ended knowledge queries.

---

## 🏗️ Architecture & Workflow

```text
       [ User Speaks ]
              │
              ▼
   ┌──────────────────────┐
   │  Microphone Input    │  (PyAudio / SpeechRecognition)
   └──────────┬───────────┘
              │
              ▼
   ┌──────────────────────┐
   │ Google Speech-to-Text│  (Converts audio -> string)
   └──────────┬───────────┘
              │
              ▼
    Wake Word = "Beast"?
     ├── No  ─► Continue Listening
     └── Yes ─► Acknowledge ("Yes")
                     │
                     ▼
        ┌─────────────────────────┐
        │ Command Intent Parser   │
        └────────────┬────────────┘
                     │
       ┌─────────────┴─────────────┐
       ▼                           ▼
[ Web Automation ]         [ Speech Output ]
(Open Sites / Apps)          (pyttsx3 TTS)
```

---

## 💬 Supported Voice Commands

| Voice Command | Action Executed |
|---|---|
| `Beast` *(Wake word)* | Activates the assistant, responds with *"Yes"*, and waits for the user's command |
| `Open Google` | Launches your default web browser and navigates to Google |
| `Open YouTube` | Opens YouTube in the browser |
| `Open LinkedIn` | Opens LinkedIn for professional networking |
| `Open Facebook` | Opens Facebook |
| `Open Instagram` | Opens Instagram |
| *Unrecognized Query* | Responds verbally with *"Sorry"* to prompt for a clearer command |

---

## 🚀 Getting Started

### 1. Prerequisites

Ensure you have **Python 3.9+** installed on your system.

On Windows, microphone capture requires `PyAudio`. If installing on Windows:
```bash
pip install pipwin
pipwin install pyaudio
```

### 2. Installation

Clone this repository and navigate to the `BEAST-main` directory:

```bash
git clone https://github.com/Sahil860534/R-project.git
cd R-project/BEAST-main
```

Install the required Python libraries:

```bash
pip install speechrecognition pyttsx3 requests
```

### 3. Running the Assistant

Run the entry point script:

```bash
python main.py
```

1. You will hear: *"Hey, I am BEAST, how may I help you?"*
2. Say **`"Beast"`** to wake the assistant.
3. Once BEAST responds with **`"Yes"`**, give your command (e.g., *"Open YouTube"* or *"Open LinkedIn"*).

---

## 📂 Project Structure

```text
BEAST-main/
├── main.py            # Core voice listening loop, command parser & automation logic
└── README.md          # Comprehensive technical documentation & user guide
```

---

## 🔮 Future Roadmap

- [ ] **Gemini API Integration:** Plug in Google Gemini 1.5 Flash for conversational reasoning and code explanation.
- [ ] **News & Weather Feeds:** Fetch live headlines and local weather via REST APIs.
- [ ] **Desktop Task Controls:** Control local system volume, take screenshots, and manage reminder timers.
- [ ] **GUI Dashboard:** Add a modern Streamlit / CustomTkinter interface showing real-time audio waveforms and history.

---

## 👨‍💻 Author

**Sahil Rane**
- **GitHub:** [@Sahil860534](https://github.com/Sahil860534)
- **Portfolio:** [https://sahil860534.github.io/portfolio/](https://sahil860534.github.io/portfolio/)
- **Email:** [ranesahil555@gmail.com](mailto:ranesahil555@gmail.com)
