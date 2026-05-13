# Texpark-
# 🛡️ Safety Route Guardian

> **Guardian AI — Intelligent Route Safety Dashboard**  
> An AI-powered platform that helps users navigate safely by recommending secure routes, issuing real-time danger alerts, providing SOS emergency support, and offering an AI chatbot for safety tips.

<p align="center">
  <img src="https://img.shields.io/badge/Status-Live-brightgreen?style=for-the-badge" />
  <img src="https://img.shields.io/badge/React-Frontend-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/FastAPI-Backend-009688?style=for-the-badge&logo=fastapi" />
  <img src="https://img.shields.io/badge/ML-Risk%20Prediction-FF6F00?style=for-the-badge&logo=python" />
  <img src="https://img.shields.io/badge/Maps-Leaflet%20%2F%20Google-34A853?style=for-the-badge&logo=googlemaps" />
</p>

---

## 🌐 Live Demo

🔗 **[https://safety-route-guardian--bharathibrbhara.replit.app/route-safety](https://safety-route-guardian--bharathibrbhara.replit.app/route-safety)**

---

## 📌 Table of Contents

- [About the Project](#about-the-project)
- [Key Features](#key-features)
- [Tech Stack](#tech-stack)
- [System Architecture](#system-architecture)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [How It Works](#how-it-works)
- [Screenshots](#screenshots)
- [Team](#team)
- [License](#license)

---

## 🔍 About the Project

**Safety Route Guardian** is an AI-driven safety navigation system designed to protect individuals — especially women, solo travelers, and vulnerable groups — from potential dangers during travel. The system combines **machine learning-based risk prediction**, **real-time danger alerts**, **intelligent route planning**, and an **emergency SOS system** into a single unified dashboard.

The project was built for a **Smart Health & Safety hackathon**, targeting the real-world problem of personal safety during commutes.

---

## ✨ Key Features

### 🗺️ 1. Safe Route Recommendation
- Analyzes historical crime data and user-reported incidents to suggest the **safest path** between two points
- Visualized on an interactive map using **Leaflet / Google Maps API**
- Multiple route options ranked by safety score

### 🚨 2. Real-Time Crime & Danger Alerts
- Displays live alerts for reported incidents in the vicinity
- Color-coded danger zones (🔴 High Risk → 🟡 Medium → 🟢 Safe)
- Proximity-based notifications when entering unsafe areas

### 🆘 3. SOS Emergency Feature
- One-click SOS button to instantly send location to emergency contacts
- Triggers alert with GPS coordinates
- Logs emergency event for tracking

### 🤖 4. AI Safety Chatbot
- Interactive chatbot powered by AI for real-time safety guidance
- Provides personalized safety tips based on location and time
- Answers queries about nearby safe zones, police stations, and hospitals

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| **Frontend** | React.js / Next.js |
| **Backend** | Python, FastAPI / Flask |
| **ML Model** | Random Forest / Scikit-learn (Risk Prediction) |
| **Maps** | Google Maps API / Leaflet.js |
| **Database** | JSON / SQLite |
| **Deployment** | Replit |
| **Styling** | Tailwind CSS |

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────┐
│               User Interface (React)             │
│   Route Input │ Map View │ SOS │ Chatbot         │
└──────────────────────┬──────────────────────────┘
                       │ API Calls
┌──────────────────────▼──────────────────────────┐
│             FastAPI / Flask Backend              │
│   Route API │ Alert API │ SOS API │ Chat API     │
└──────────────────────┬──────────────────────────┘
                       │
          ┌────────────┴─────────────┐
          │                          │
┌─────────▼──────────┐   ┌──────────▼──────────┐
│   ML Risk Engine   │   │  Maps / Geo Service  │
│ (Random Forest)    │   │ (Google Maps/Leaflet) │
│ Safety Score       │   │ Route Calculation     │
└────────────────────┘   └─────────────────────┘
```

---

## 📁 Project Structure

```
safety-route-guardian/
│
├── frontend/                   # React / Next.js Application
│   ├── pages/
│   │   └── route-safety.jsx    # Main Safety Dashboard
│   ├── components/
│   │   ├── MapView.jsx          # Interactive Map
│   │   ├── SOSButton.jsx        # Emergency SOS
│   │   ├── AlertPanel.jsx       # Danger Alerts
│   │   └── SafetyChatbot.jsx    # AI Chatbot
│   └── public/
│
├── backend/                    # Python FastAPI / Flask Server
│   ├── main.py                 # API Entry Point
│   ├── routes/
│   │   ├── route_api.py        # Safe Route Endpoints
│   │   ├── alert_api.py        # Real-time Alert Endpoints
│   │   ├── sos_api.py          # SOS Endpoints
│   │   └── chat_api.py         # Chatbot Endpoints
│   └── ml/
│       ├── model.pkl            # Trained ML Model
│       ├── predict.py           # Risk Prediction Logic
│       └── train.py             # Model Training Script
│
├── data/
│   └── crime_data.csv           # Historical Incident Dataset
│
├── requirements.txt
├── package.json
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.9+
- Node.js 18+
- Google Maps API Key (or Leaflet for open-source)

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/safety-route-guardian.git
cd safety-route-guardian
```

### 2. Backend Setup

```bash
cd backend
pip install -r requirements.txt
uvicorn main:app --reload
```

The API will be running at `http://localhost:8000`

### 3. Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

The app will be running at `http://localhost:3000`

### 4. Environment Variables

Create a `.env` file in the root:

```env
GOOGLE_MAPS_API_KEY=your_api_key_here
BACKEND_URL=http://localhost:8000
```

---

## ⚙️ How It Works

### ML Risk Prediction

1. **Data**: Historical crime/incident data is processed with location, time, and type features
2. **Model**: A **Random Forest Classifier** is trained to predict danger score (0–100) for a given area
3. **Output**: Each route segment gets a safety score; the system recommends the route with the highest overall score

### Route Safety Score Formula

```
Safety Score = (1 - Crime Density) × Time Weight × Lighting Factor × Crowd Factor
```

### Real-Time Alerts

- Incident reports are fetched via API every few minutes
- Alerts are rendered as pins/zones on the map
- Users receive proximity warnings as they navigate

---

## 📸 Screenshots

> _Add screenshots of your dashboard, map view, SOS screen, and chatbot here_

| Feature | Preview |
|---------|---------|
| 🗺️ Safety Map | ![Map View](screenshots/map.png) |
| 🚨 Danger Alerts | ![Alerts](screenshots/alerts.png) |
| 🆘 SOS Panel | ![SOS](screenshots/sos.png) |
| 🤖 AI Chatbot | ![Chatbot](screenshots/chatbot.png) |

---

## 👩‍💻 Team

| Name | Role |
|------|------|
| **Bharathi** | Full Stack Developer, ML Engineer |
| _(Add teammates)_ | _(Add roles)_ |

**College:** ATME College of Engineering, Mysore  
**Department:** Computer Science & Engineering  
**Event:** Smart Safety Hackathon

---

## 🏆 Highlights

- ✅ End-to-end ML pipeline for safety risk prediction
- ✅ Real-time interactive safety map
- ✅ One-click SOS emergency system
- ✅ AI-powered safety chatbot
- ✅ Deployed live on Replit

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgements

- [Leaflet.js](https://leafletjs.com/) — Open-source maps
- [Google Maps Platform](https://developers.google.com/maps)
- [FastAPI](https://fastapi.tiangolo.com/) — Python backend framework
- [Scikit-learn](https://scikit-learn.org/) — ML library
- [Replit](https://replit.com/) — Deployment platform

---

<p align="center">
  Made with ❤️ for a Safer World · <strong>Guardian AI</strong>
</p>


## 🌐 Live Demo
🔗 https://guardian-route-safety--chathurthirevan.replit.app/

🔗 [https://safety-route-guardian--bharathibrbhara.replit.app/route-safety](https://safety-route-guardian--bharathibrbhara.replit.app/route-safety)
