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
```


### 📚 Libraries Used

Below are the libraries used throughout the project, grouped and explained for clarity.

## 🔧 Core Python Libraries
```json```

Used for saving & loading conversation history in .json format.

```os```

Handles environment variables, file paths, and file clean-ups.

```datetime```

Fetches live time info to include in the system prompt.

```re```

Used for regex filtering to remove emojis / markdown before TTS output.

```time```

Used for pauses, handling delays, and timing operations in audio processing.

### 🌐 Networking & API Libraries
```requests```

Performs external API calls including weather (Open-Meteo) and TMDB movie search.

```dotenv (load_dotenv)```

Loads API keys (GROQ_API_KEY, TMDB_API_KEY) from .env file securely.

### 🤖 AI Interaction
```groq```

Used to call Groq LLM (Llama 3.1) for generating conversational responses.

### 🎙 Audio Input / Output Libraries
```speech_recognition```

Handles speech-to-text using Google STT API.

```pyaudio```

Records microphone audio in raw PCM format.

```wave```

Saves raw byte-stream frames into .wav audio files.

```sounddevice```

Used to play final generated speech audio.

```pydub```

Converts MP3 → WAV, handles buffering, helps playback preparation.

```edge_tts```

Generates Text-to-Speech using Microsoft Edge Neural TTS voices.

```io```

Handles in-memory audio buffers for TTS playback.

### 🔊 Audio Processing & Noise Reduction
```numpy```

Performs array transformations for audio analysis & TTS playback.

```scipy.io.wavfile```

Used to read/write numeric WAV data for denoising.

```noisereduce```

Applies deep learning–based noise reduction on recorded voice commands.

### 🏠 Hardware Interaction
```RPi.GPIO```

Controls Raspberry Pi GPIO pins (optional future extension: LED, button, sensor triggers).

### 📦 Project Overview

This project is a fully offline + online hybrid voice assistant, named Arav, powered by:

```
Groq Llama 3.1 model

Google Speech Recognition

Microsoft Edge Neural TTS

Noise-reduced microphone input

Wake-word detection

Location-aware weather

Conversational memory
```

### ⚙️ Core Architecture Summary
## 1. Wake-Word Listener

Continuously records 3-second audio chunks and checks if the user said:

["arav", "ara", "aarav", "naru", "hey naru"]

### 2. Voice Command Recording

Once awakened, it records a 7-second command:

```
Applies noise reduction

Converts to WAV

Sends to Google STT
```

### 3. Command Understanding

Processes:
```
Voice switching

Location change

Sleep mode

Movie queries

Weather questions
```
### 4. LLM Interaction

Forms a system prompt including:
```
Time

Weather

Location

Personality profile (Hinglish, witty, meme-ish)

Movie recommendation

```
Then calls Groq API for reply.

### 5. Speech Output

Cleans text of emojis & markdown → sends to Edge TTS → plays via sounddevice.
```
📁 Important Configurations
Audio Settings:
MIC_SAMPLE_RATE = 16000
MIC_CHANNELS = 1
MIC_FORMAT = pyaudio.paInt16
MIC_CHUNK_SIZE = 1024
```
Filenames:
```
temp_raw_audio.wav  
temp_clean_audio.wav  
conversation_history.json
```
🔥 Why this Architecture Works Great
```
✔ Lightweight
✔ Super fast (Groq inference)
✔ Good noise reduction
✔ Real conversational memory
✔ Wake-word based hands-free experience
✔ Human-like Hinglish personality
```
🚀 Running the App
1. Install Dependencies
```
pip install -r requirements.txt
```

2. Add your .env file:
```
GROQ_API_KEY=your_key
TMDB_API_KEY=your_key
```
3. Run:
```
python main.py
```
### Arav waits for your voice: “hey Arav”
→ processes your command
→ responds naturally.
