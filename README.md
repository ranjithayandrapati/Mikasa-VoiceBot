# Mikasa VoiceBot

Mikasa VoiceBot is an intelligent voice assistant project designed to recognize, process, and respond to user commands using cutting-edge speech-to-text, natural language processing (NLP), and text-to-speech technologies. The project provides a modular and extensible framework for building customizable voice-based assistants.

## Table of Contents

- [Features](#features)
- [Architecture](#architecture)
- [Getting Started](#getting-started)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Extending Mikasa VoiceBot](#extending-mikasa-voicebot)
- [Project Structure](#project-structure)
- [Dependencies](#dependencies)
- [Troubleshooting](#troubleshooting)
- [License](#license)

---

## Features

- 🎤 **Voice Command Recognition**: Converts spoken language into text using speech-to-text engines.
- 🤖 **Natural Language Understanding**: Processes and understands user intents with NLP models.
- 🗣️ **Contextual Response Generation**: Responds to queries with dynamic, context-aware answers.
- 🔄 **Text to Speech**: Converts text responses back to speech for seamless interaction.
- 🔌 **Extensible Skills**: Plug-in architecture allows easy addition of new skills/integrations.
- 🏃 **Cross-platform Support**: Works on Windows, macOS, Linux.(implemented in windows)

---

## Architecture

```
┌──────────────┐      ┌─────────────┐      ┌─────────────┐      ┌──────────────┐
│  Microphone  │ ──▶ │ Speech-to-  │ ──▶ │   NLP/NLU   │ ──▶ │  Skill/Action │
│   Input      │     │   Text      │     │ Processing  │     │   Execution   │
└──────────────┘     └─────────────┘     └─────────────┘     └──────────────┘
                                                                │
                                                                ▼
                                                        ┌─────────────┐
                                                        │Text-to-Speech│
                                                        │   Output    │
                                                        └─────────────┘
```

---

## Getting Started

### Prerequisites

- Python 3.8+
- Microphone and speakers/headphones
- (Optional) API keys for external speech/NLP services

---

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/ranjithayandrapati/Mikasa-VoiceBot.git
   cd Mikasa-VoiceBot
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **(Optional) Configure environment variables or API keys**
   - See [Configuration](#configuration) for details.

---

## Usage

1. **Start the voicebot:**
   ```bash
   python agent.py console (in VS code)
   python agent.py dev (to run in livekit playground)
   ```

2. **Interact using your voice!**
   - Speak commands into your microphone.
   - Mikasa VoiceBot will recognize your command, process it, and respond.

3. **Example commands:**
   - "What time is it?"
   - "Tell me a joke."
   - "What's the weather like?"
   - "Open YouTube."

---

## Configuration

- Edit the `.env` file for settings such as:
  - Speech-to-text engine/API (e.g., Google, Vosk, Azure)
  - NLP provider (e.g., spaCy, transformers, Rasa)
  - Hotword detection settings
  - Custom skills enable/disable

---

## Extending Mikasa VoiceBot

**To add a new skill:**
1. Create a Python file in the `skills/` directory.
2. Implement a class or function with a decorator or registration method.
3. Add logic for intent recognition and action execution.
4. Register your skill in `skills/__init__.py` or via plugin loader.

**Example:**
```python
# skills/weather.py

from voicebot.skills import register_skill

@register_skill('weather')
def tell_weather(query):
    # Your weather API logic here
    return "It's sunny and 25°C today."
```

---

## Project Structure

```
Mikasa-VoiceBot/
├── agent.py
├── requirements.txt
├── .env
├── tools.py
├── prompts.py
└── README.md
```


## Dependencies

- `Livekit account`
- `Google peoject Key`
- `transformers`, `spacy`, or `rasa` (for NLP)
- See `requirements.txt` for the full list

---

## Troubleshooting

- **Microphone not detected:** Check your device settings and ensure the correct input is selected.
- **No response:** Ensure your dependencies are installed, and check logs for errors.
- **API errors:** Double-check your API keys and network connection.

---

## License

This project is licensed under the MIT License. See [`LICENSE`](LICENSE) for details.

---

## Credits

Developed and maintained by [ranjithayandrapati](https://github.com/ranjithayandrapati).

---

## Contributions

Pull requests, bug reports, and suggestions are welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.
