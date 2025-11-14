# Arav AI 🤖✨  
Multi-Domain-Humanized-AI-Assistant

Arav is a highly responsive, voice-activated AI assistant with a unique Hinglish personality. Built with Python, Groq, and state-of-the-art speech technologies, Arav is designed to be a helpful, context-aware, and engaging companion.

---

## 🚀 Features

- **Voice-Activated:** Hands-free operation using wake words ("Hey Arav").
- **High-Speed Responses:** Powered by the **Groq LPU™ Inference Engine** with the Llama 3.1 model for near-instantaneous replies.
- **Unique Personality:** A custom "Hinglish" persona that makes interactions feel natural and fun.
- **Context-Aware:** Knows the current time, date, and your location for relevant answers.
- **Real-time Weather:** Integrated with Open-Meteo for live weather updates.
- **Noise Reduction:** Cleans microphone input for better recognition in noisy environments.
- **Switchable Voices:** Choose between male or female voice output.
- **Conversation Memory:** Remembers recent dialogue for follow-up questions.
- **Extensible Skills:**  
  - Movie Recommendations  
  - Finding Places  
  - Emotional Support Conversations  
  - Weather Forecasting  
  - Fashion Tips  
  - General Talk and Q&A  

---

## 🛠️ How It Works

Arav operates on a simple yet effective loop: **Listen → Process → Think → Respond**

1. **Wake Word Detection:** Listens passively for "Hey Arav".
2. **Command Recording:** Starts recording after activation.
3. **Audio Processing:** Cleans audio via noise reduction algorithms.
4. **Speech-to-Text (STT):** Converts speech to text using Google STT.
5. **Context Assembly:** Combines the user's query, history, time, and weather.
6. **LLM Inference:** Sends the context to Groq for an intelligent, Hinglish-style response.
7. **Text-to-Speech (TTS):** Converts the response into natural-sounding audio.
8. **Audio Playback:** Plays the response instantly.

---

## 🔧 Tech Stack

- **LLM Engine:** Groq (Llama 3.1 8B Instant)
- **STT:** `speech_recognition` (Google STT)
- **TTS:** `edge-tts`
- **Audio Processing:** `pyaudio`, `pydub`, `sounddevice`, `noisereduce`
- **APIs:** Open-Meteo, TMDB
- **Language:** Python 3.9+
- **Async Framework:** `asyncio`

---

## ⚙️ Setup and Installation

### Prerequisites

- Python 3.9+
- API Keys:
  - GroqCloud
  - TMDB (optional but recommended)
- System dependencies for PyAudio:
  - **Debian/Ubuntu/Raspberry Pi OS**
    ```bash
    sudo apt-get update && sudo apt-get install portaudio19-dev
    ```
  - **macOS**
    ```bash
    brew install portaudio
    ```

---

### Installation Steps

1. **Clone the repository**
    ```bash
    git clone https://github.com/your-username/arav-ai.git
    cd arav-ai
    ```

2. **Create & activate a virtual environment**
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

3. **Install dependencies**
    ```bash
    pip install -r requirements.txt
    ```

4. **Set environment variables**  
   Create a `.env` file in the root directory:

    ```env
    GROQ_API_KEY="gsk_YourGroqApiKeyHere"
    TMDB_API_KEY="YourTmdbApiKeyHere"
    ```

---

## 📦 requirements.txt

```txt
groq
requests
speechrecognition
edge-tts
python-dotenv
pydub
numpy
sounddevice
pyaudio
scipy
noisereduce
