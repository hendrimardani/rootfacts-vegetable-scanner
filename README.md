# 🌱 RootFacts - AI Vegetable & Fruit Recognition

A Progressive Web App (PWA) that leverages artificial intelligence to recognize vegetables and fruits in real-time through the device camera, then generates unique fun facts using generative AI.

## ✨ Key Features

- **📷 Real-Time Detection** — Live camera streaming with automatic object detection powered by TensorFlow.js
- **🤖 AI Fun Facts** — Generates unique facts for each detected vegetable/fruit using Transformers.js
- **🎭 Dynamic Persona** — Choose AI writing style: Normal, Funny, Professional, or Casual
- **⚡ Adaptive Backend** — Automatically uses WebGPU if available, falls back to WebGL/WASM
- **🎯 FPS Limiter** — Configurable camera FPS (15–60) via UI slider
- **📋 Copy to Clipboard** — Copy fun facts with one click, with smooth toast notification
- **📱 PWA & Offline** — Installable as a native app, works offline with precached assets and AI model
- **📊 Loading Indicator** — Displays progress percentage during model initialization

## 🛠️ Tech Stack

| Technology | Purpose |
|-----------|---------|
| **React 19** | UI library / component architecture |
| **Vite 6** | Build tool & dev server |
| **TensorFlow.js** | Object detection (MobileNetV2 / Teachable Machine) |
| **Transformers.js** | AI text generation (LaMini-Flan-T5-77M) |
| **Workbox** | Service Worker & precaching |
| **Lucide React** | UI icons |

## 📁 Project Structure

```
rootfacts-react/
├── public/
│   ├── icons/              # PWA icons (192x192, 512x512)
│   ├── model/              # Local AI model
│   │   ├── model.json      # Model architecture (MobileNetV2)
│   │   ├── metadata.json   # Class labels (12 fruits/vegetables)
│   │   └── weights.bin     # Model weights
│   ├── manifest.json       # Web App Manifest
│   └── sw.js               # Service Worker (Workbox)
├── src/
│   ├── components/
│   │   ├── CameraSection.jsx   # Camera, FPS & tone controls
│   │   ├── Header.jsx          # Header & model status
│   │   └── InfoPanel.jsx       # Detection results & fun facts
│   ├── services/
│   │   ├── CameraService.js    # Camera & stream management
│   │   ├── DetectionService.js # Object detection (TF.js)
│   │   └── RootFactsService.js # Fact generation (Transformers.js)
│   ├── hooks/
│   │   └── useAppState.js      # State management (useReducer)
│   ├── utils/
│   │   ├── config.js           # App & tone configuration
│   │   ├── common.js           # Helper functions
│   │   └── ui.js               # Style constants
│   ├── App.jsx                 # Main component
│   ├── main.jsx                # Entry point
│   └── index.css               # Stylesheet
├── sw.js                       # Service Worker (source)
├── index.html                  # Main HTML
├── vite.config.js              # Vite & PWA configuration
├── package.json
└── STUDENT.txt                 # Deployment URL
```

## 🚀 Getting Started

### Prerequisites
- Node.js >= 18
- Modern browser (Chrome/Edge recommended)

### Installation & Development

```bash
# Clone the repository
git clone https://github.com/<username>/rootfacts-react.git
cd rootfacts-react

# Install dependencies
npm install

# Start development server
npm run dev
```

The app runs at `http://localhost:3001`

### Production Build

```bash
npm run build
npm run preview
```

## 🎯 Supported Labels

The model can recognize 12 types of fruits and vegetables:

| # | Label |
|---|-------|
| 1 | Apple |
| 2 | Banana |
| 3 | Grape |
| 4 | Lemons |
| 5 | Kiwi |
| 6 | Mango |
| 7 | Orange |
| 8 | Pear |
| 9 | Pineapple |
| 10 | Pomegranate |
| 11 | Tomato |
| 12 | Watermelon |

## 📱 PWA & Offline Support

This app supports:

- **Installable** — Can be installed to home screen / desktop
- **Offline Detection** — AI model is precached so detection works without internet
- **Precaching** — All core assets (HTML, CSS, JS, model files) are cached by the Service Worker

## 🌐 Deployment

The app is deployed to **Netlify**. The deployment URL is listed in `STUDENT.txt`.

## 📄 License

This project was created for educational purposes.
