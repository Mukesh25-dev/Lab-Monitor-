# Lab-Monitor-


# 🔬 Smart Lab Environment Monitor

![React](https://img.shields.io/badge/Frontend-React-blue?style=flat-square&logo=react)
![FastAPI](https://img.shields.io/badge/Backend-FastAPI-009688?style=flat-square&logo=fastapi)
![Tailwind](https://img.shields.io/badge/UI-TailwindCSS-38B2AC?style=flat-square&logo=tailwindcss)
![Raspberry Pi](https://img.shields.io/badge/Hardware-Raspberry%20Pi-C51A4A?style=flat-square&logo=raspberrypi)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)

---

## 🧠 Overview

**Smart Lab Environment Monitor** is a **real-time IoT dashboard** that visualizes live environmental and electrical parameters from a research laboratory.  
It uses a **Raspberry Pi** connected to sensors and a **digital multimeter**, streaming data to a **React + FastAPI** dashboard.

The interface features smooth **Apple-style ring gauges**, **historical trend charts**, and **real-time updates**—making it ideal for labs, classrooms, and industrial environments.

---

## ✨ Features

- ⚡ **Live Data Streaming** – Fetches sensor data every 2 seconds from Raspberry Pi via FastAPI  
- 📊 **Interactive Charts** – Recharts-based visualization for multiple time durations  
- 🔵 **Dynamic Gauges** – Beautiful gradient ring meters for real-time values  
- 💻 **Responsive & Modern UI** – Tailwind CSS with glassy gradient background  
- 🧠 **Optimized Rendering** – Memoized components to prevent flicker  
- 🧩 **Modular Design** – Easy to extend for new sensors or parameters  

---

## 🛠️ Tech Stack

| Layer | Technologies |
|-------|---------------|
| **Frontend** | React 18, Vite, Tailwind CSS, Recharts, React Icons |
| **Backend** | FastAPI (Python 3) |
| **Hardware** | Raspberry Pi 4 B, DHT22 Sensor, Digital Multimeter |
| **Transport** | REST API (`/current`, `/averaged`) |
| **Hosting Options** | GitHub Pages / Vercel / Netlify |

---

## 🧩 System Architecture

┌────────────────────────────┐
│ DHT22 Sensor & Multimeter│
└─────────────┬──────────────┘
│
Raspberry Pi (FastAPI)
│
REST API (JSON Output)
│
React Dashboard (PC)


---

## ⚙️ API Endpoints

### `GET /current`
Returns the latest readings:
```json
{
  "temperature": 25.48,
  "humidity": 86.5,
  "earth_neutral_voltage": 0.535,
  "timestamp": "2025-11-11 07:24"
}

GET /averaged?duration=1d

Returns averaged readings for a time range (1h, 6h, 1d, 1w, 1m):

{
  "count": 840,
  "data": [
    {"timestamp": "2025-11-10 08:00", "temperature": 25.3, "humidity": 86.1, "earth_neutral_voltage": 0.53},
    ...
  ]
}

🧱 Project Structure
smart-lab-environment-monitor/
│
├── src/
│   ├── components/
│   │   └── GaugeDashboard.jsx   # Main dashboard logic
│   ├── App.jsx
│   └── index.jsx
│
├── package.json
├── tailwind.config.js
├── vite.config.js
└── README.md

🖥️ Dashboard Preview
Gauges Section	Chart Section

	

(Add your own screenshots to screens/ folder for better presentation.)

🧰 Setup & Installation
1️⃣ Clone the Repository
git clone https://github.com/<your-username>/smart-lab-environment-monitor.git
cd smart-lab-environment-monitor

2️⃣ Install Dependencies
npm install

3️⃣ Start the Frontend
npm run dev


Then open:
👉 http://127.0.0.1:5173

4️⃣ Run FastAPI Backend on Raspberry Pi
uvicorn main:app --host 0.0.0.0 --port 8000


Ensure these endpoints work:

http://<pi-ip>:8000/current
http://<pi-ip>:8000/averaged


Update your frontend API URLs if necessary.

🔌 Hardware Setup
Component	Role
Raspberry Pi 4B	Hosts the FastAPI backend
DHT22 Sensor	Measures Temperature & Humidity
Digital Multimeter (USB)	Reads Earth-Neutral Voltage
Breadboard + Jumper Wires	Circuit connections
5V Power Supply	Power source for Pi & sensors
💡 Future Enhancements

🚨 Threshold alerts & color-based warnings

📲 Mobile-friendly dashboard version

☁️ Cloud data storage & analytics

📤 Export logs as CSV or PDF

🔔 Notification system (email / SMS)

👨‍💻 Author

Your Name
🔗 GitHub

🔗 LinkedIn

🪪 License

This project is licensed under the MIT License.
See LICENSE
 for more details.

🌍 “Smart Lab Systems – Real-time insights powered by Raspberry Pi & React.”

