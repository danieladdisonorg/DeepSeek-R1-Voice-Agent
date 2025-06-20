# DeepSeek R1 AI Voice Agent

A real-time AI voice assistant powered by DeepSeek R1 that enables seamless voice conversations through speech-to-text transcription, AI response generation, and text-to-speech synthesis.

## 🌟 Overview

This project creates an interactive AI voice agent that:
- Captures and transcribes speech in real-time using AssemblyAI
- Generates intelligent responses using DeepSeek R1 (7B model) via Ollama
- Converts AI responses back to natural speech using ElevenLabs
- Streams audio responses for immediate playback

## ✨ Features

- **Real-time Speech Recognition**: High-quality speech-to-text transcription with AssemblyAI
- **Advanced AI Responses**: Powered by DeepSeek R1's reasoning capabilities
- **Natural Voice Synthesis**: Professional text-to-speech with ElevenLabs
- **Streaming Audio Playback**: Low-latency audio streaming for responsive conversations
- **Conversation Memory**: Maintains context throughout the conversation
- **Cross-platform Support**: Works on macOS, Linux, and Windows

## 🔧 Prerequisites

### API Keys Required
- **AssemblyAI API Key**: [Get your free API key](https://www.assemblyai.com/?utm_source=youtube&utm_medium=referral&utm_campaign=yt_smit_28)
- **ElevenLabs API Key**: [Sign up for ElevenLabs](https://elevenlabs.io/)

### System Dependencies

#### Install Ollama
Download and install Ollama from [ollama.com](https://ollama.com/)

#### Install PortAudio
**Ubuntu/Debian:**
```bash
sudo apt update && sudo apt install portaudio19-dev
```

**macOS:**
```bash
brew install portaudio
```

**Windows:**
PortAudio is typically included with the Python package installation.

#### Install MPV (macOS only)
```bash
brew install mpv
```

## 📦 Installation

### 1. Clone the Repository
```bash
git clone https://github.com/danieladdisonorg/DeepSeek-R1-Voice-Agent.git
cd DeepSeek-R1-Voice-Agent
```

### 2. Install Python Dependencies
```bash
pip install "assemblyai[extras]" ollama elevenlabs
```

### 3. Download DeepSeek R1 Model
```bash
ollama pull deepseek-r1:7b
```

### 4. Configure API Keys
Edit `AIVoiceAgent.py` and replace the placeholder API keys:
```python
aai.settings.api_key = "YOUR_ASSEMBLYAI_API_KEY"
self.client = ElevenLabs(api_key="YOUR_ELEVENLABS_API_KEY")
```

## 🚀 Usage

### Start the Voice Agent
```bash
python AIVoiceAgent.py
```

### Interaction Flow
1. **Speak**: The agent listens for your voice input
2. **Processing**: Your speech is transcribed and sent to DeepSeek R1
3. **Response**: The AI generates a response (limited to 300 characters for quick interactions)
4. **Playback**: The response is converted to speech and played back
5. **Continue**: The conversation continues with maintained context

### Stopping the Agent
Press `Ctrl+C` to stop the voice agent.

## ⚙️ Configuration

### Model Settings
- **AI Model**: DeepSeek R1 7B (configurable in the code)
- **Voice Model**: ElevenLabs Turbo v2 (configurable)
- **Response Length**: Limited to 300 characters (adjustable in system prompt)
- **Sample Rate**: 16kHz for optimal quality

### Customization Options
- Modify the system prompt in `AIVoiceAgent.py` to change AI behavior
- Adjust response length limits
- Change voice models in ElevenLabs configuration
- Modify audio streaming parameters

## 🔍 Troubleshooting

### Common Issues

**"No module named 'assemblyai'"**
```bash
pip install "assemblyai[extras]"
```

**"Ollama connection error"**
- Ensure Ollama is running: `ollama serve`
- Verify the model is downloaded: `ollama list`

**"Audio device not found"**
- Check microphone permissions
- Verify PortAudio installation
- Test microphone with other applications

**"ElevenLabs API error"**
- Verify API key is correct
- Check API quota/usage limits
- Ensure stable internet connection

### Performance Tips
- Use a quality microphone for better transcription accuracy
- Ensure stable internet connection for API calls
- Close unnecessary applications to free up system resources

## 🏗️ Architecture

```
┌─────────────────┐    ┌──────────────┐    ┌─────────────────┐
│   Microphone    │───▶│  AssemblyAI  │───▶│   DeepSeek R1   │
│   (Audio Input) │    │ (Speech-to-  │    │ (AI Response    │
└─────────────────┘    │  Text)       │    │  Generation)    │
                       └──────────────┘    └─────────────────┘
                                                      │
┌─────────────────┐    ┌──────────────┐              │
│   Speakers      │◀───│  ElevenLabs  │◀─────────────┘
│ (Audio Output)  │    │ (Text-to-    │
└─────────────────┘    │  Speech)     │
                       └──────────────┘
```

## 📄 License

This project is open source. Please check the repository for license details.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues, feature requests, or pull requests.

## 📞 Support

For issues and questions:
- Open an issue on GitHub
- Check the troubleshooting section above
- Review API documentation for AssemblyAI, Ollama, and ElevenLabs

---

**Note**: This project requires active internet connection for API services and sufficient system resources to run the DeepSeek R1 model locally via Ollama.
