# 🌾 Krishi Samadhan - Agri-Advisor

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Azure Speech](https://img.shields.io/badge/Azure-Speech_Services-0078D4?style=flat&logo=microsoft-azure)](https://azure.microsoft.com/en-us/services/cognitive-services/speech-services/)
[![Perplexity API](https://img.shields.io/badge/Perplexity-API-purple?style=flat)](https://www.perplexity.ai/)
[![Google Gemini](https://img.shields.io/badge/Google-Gemini_AI-4285F4?style=flat&logo=google)](https://ai.google.dev/)

An intelligent, multilingual agricultural advisory chatbot designed to assist farmers, traders, and agricultural professionals with real-time, context-aware guidance. Krishi Samadhan combines AI-powered text and voice interactions with location-based weather data to deliver personalized agricultural solutions.

## ✨ Features

### 🗣️ Dual Interaction Modes
- **Text Mode**: Traditional text-based chat interface
- **Speech Mode**: Voice-to-voice conversation using Azure Speech Services
- Seamless switching between modes

### 🌐 Multilingual Support
Supports 7 Indian languages with native speech recognition and synthesis:
- English (en-IN)
- Hindi (hi-IN)
- Marathi (mr-IN)
- Tamil (ta-IN)
- Bengali (bn-IN)
- Punjabi (pa-IN)
- Gujarati (gu-IN)

### 🤖 Advanced AI Capabilities
- **Multiple AI Models**: Choose from Perplexity's Sonar models, Mistral, CodeLlama, and Llama 2
- **Image Analysis**: Upload or capture crop images for instant AI-powered diagnosis using Google Gemini Vision
- **Document Context**: Upload `.txt` or `.pdf` files for context-aware agricultural advice
- **Reasoning Display**: View the AI's step-by-step thinking process behind each answer

### 📍 Location-Aware Intelligence
- Automatic geolocation detection
- Real-time weather integration (temperature, wind speed)
- Localized agricultural recommendations based on your region

### 📊 Analytics Dashboard
- Track total questions asked
- Monitor current session statistics
- Export usage data as JSON
- Reset counter functionality

### 🎯 User Experience
- Modern, responsive UI with smooth animations
- Dark/light theme support
- Adaptive mobile design
- File and image preview with easy removal
- Bot response control (pause/resume speech)

## 🚀 Getting Started

### Prerequisites

You need API keys for:
1. **Azure Speech Services** - For voice recognition and synthesis
2. **Perplexity API** - For AI-powered text responses
3. **Google Gemini API** - For image analysis

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/krishi-samadhan.git
cd krishi-samadhan
```

2. **Configure API Keys**

Open the HTML file and locate the `API_CONFIG` object (around line 520):

```javascript
const API_CONFIG = {
    gemini: {
        key: 'YOUR_GOOGLE_GEMINI_API_KEY'
    },
    perplexity: {
        key: 'YOUR_PERPLEXITY_API_KEY'
    },
    azure: {
        key: 'YOUR_AZURE_SPEECH_KEY',
        region: 'YOUR_AZURE_REGION' // e.g., 'centralindia'
    }
};
```

3. **Launch the application**

Simply open `index.html` in a modern web browser:
```bash
open index.html  # macOS
start index.html # Windows
xdg-open index.html # Linux
```

Or use a local server:
```bash
python -m http.server 8000
# Visit http://localhost:8000
```

## 🔧 Configuration

### AI Model Selection

Choose from multiple AI models in the settings panel:
- **Sonar Pro** (Recommended): Advanced web-search-enabled model with comprehensive answers
- **Sonar Medium Online**: Balanced model with web search capabilities
- **Sonar Small Online**: Fast model with basic web search
- **Mistral 7B Instruct**: Balanced open-source model
- **CodeLlama 34B**: Specialized for code-related tasks
- **Llama 2 70B Chat**: Large model with extensive knowledge

### System Prompt Customization

The system prompt defines the AI's behavior. Default prompt:
```
You are a multilingual agriculture AI assistant. Your name is 'Krishi Samadhan'. 
You are here to help farmers, traders, and other people in the agriculture industry. 
Please provide accurate, detailed, and well-structured answers to agriculture-related 
questions about topics like inputs, crops, harvesting, finance, and policies.
```

Customize this in the Settings panel to adjust the AI's personality and expertise.

## 📱 Usage

### Text Mode
1. Type your agricultural question in the input field
2. Optionally attach a document (`.txt` or `.pdf`) for context
3. Optionally upload/capture an image of your crop
4. Click "Send" or press Enter
5. View the AI's reasoning process by clicking "Show Reasoning"

### Speech Mode
1. Click the mode toggle to switch to Speech Mode
2. Grant microphone permissions when prompted
3. Speak your question in your preferred language
4. The AI responds with voice output
5. Conversation continues automatically

### Document Upload
- Click the 📎 icon to upload `.txt` or `.pdf` files
- Maximum file size: 5MB
- The AI uses document content as context for answers

### Image Analysis
- Click the 📸 icon to capture or upload crop images
- Choose "Take Photo" to use your device camera
- Choose "Upload from Gallery" to select an existing image
- The AI analyzes the image using Google Gemini Vision

## 🏗️ Architecture

### Tech Stack
- **Frontend**: Pure HTML5, CSS3, JavaScript (ES6+)
- **Speech Recognition**: Azure Cognitive Services Speech SDK
- **AI Models**: Perplexity AI API, Google Gemini API
- **PDF Processing**: PDF.js library
- **Geolocation**: Browser Geolocation API
- **Weather**: Open-Meteo API

### Key Components

**Speech Recognition**
```javascript
class AzureSpeechRecognizer {
    // Handles continuous speech recognition
    // Supports 7 Indian languages
    // Real-time transcription display
}
```

**File Processing**
- PDF text extraction using PDF.js
- Plain text file reading
- Base64 image encoding for API transmission

**State Management**
- LocalStorage for settings persistence
- Session tracking for analytics
- File context management

## 🎨 UI Components

### Color Scheme
```css
--primary-color: #4CAF50 (Agricultural Green)
--accent-color: #FFC107 (Harvest Amber)
--background-light: #f1f8e9
--background-card: #ffffff
```

### Responsive Design
- Desktop: Full-featured layout with sidebar settings
- Tablet: Optimized touch targets
- Mobile: Stacked layout with adaptive controls

## 📊 Analytics

The app tracks:
- Total questions asked (persistent)
- Questions in current session
- Session duration
- Language preference
- Model usage

Export format:
```json
{
  "totalQuestions": 42,
  "sessionQuestions": 5,
  "sessionDuration": 15,
  "exportDate": "11/9/2025, 2:30:00 PM",
  "language": "hi",
  "model": "sonar-pro"
}
```

## 🔒 Privacy & Security

- All API keys are configured client-side (replace with backend proxy for production)
- Location data is requested with user permission
- No data is stored on external servers beyond API providers
- LocalStorage used only for user preferences

## 🐛 Known Limitations

- Requires active internet connection
- API rate limits apply based on your service tier
- Speech recognition accuracy varies by accent and environment
- PDF processing limited to text-based PDFs (no OCR)

## 🚀 Future Enhancements

- [ ] Backend API proxy for secure key management
- [ ] Offline mode with cached responses
- [ ] Multi-turn conversation history
- [ ] Crop disease database integration
- [ ] Market price tracking
- [ ] Government scheme notifications
- [ ] Community forum integration

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Your Name**
- IIT Kanpur, 4th Year Undergraduate
- [GitHub](https://github.com/yourusername)
- [LinkedIn](https://linkedin.com/in/yourprofile)

## 🙏 Acknowledgments

- Azure Cognitive Services for speech capabilities
- Perplexity AI for intelligent responses
- Google Gemini for vision analysis
- Open-Meteo for weather data
- OpenStreetMap for geocoding

## 📞 Support

For issues, questions, or suggestions:
- Open an issue on GitHub
- Contact: your.email@example.com

---

<div align="center">

**🌾 Built with ❤️ for farmers by IIT Kanpur**

[Demo](https://your-demo-link.com) • [Report Bug](https://github.com/yourusername/krishi-samadhan/issues) • [Request Feature](https://github.com/yourusername/krishi-samadhan/issues)

</div>
