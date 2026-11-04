Night Patrol Lookup System
A modern, full-stack application designed for secure, fast, and reliable lookup of incident reports, patrol shift statuses, and operational logs in real-time.

📌 Features
🔍 Real-time Record Lookups: Fast, low-latency querying by record or incident ID.

🔒 Built-in Security: API rate limiting, dynamic HTTP security headers (via Helmet), and CORS controls.

🎨 Modern Dark UI: Responsive interface crafted with React, Tailwind CSS, and Lucide icons.

🚀 RESTful Architecture: Fully structured API supporting both GET query parameters and POST request payloads.

🛠️ Tech Stack
Frontend
Framework: React

Styling: Tailwind CSS

Icons: Lucide React

Backend
Runtime: Node.js

Framework: Express.js

Security & Utilities: helmet, cors, express-rate-limit

📂 Project Structure
night-patrol-lookup/
├── client/                 # React Frontend Application
│   ├── src/
│   │   ├── components/     # UI Components
│   │   ├── App.jsx         # Main App Component
│   │   └── index.css       # Tailwind Directives & Styles
│   ├── package.json
│   └── tailwind.config.js
│
├── server/                 # Node.js Express API
│   ├── index.js            # Express application entry point
│   └── package.json
│
└── README.md               # Project documentation
🚀 Getting Started
Prerequisites
Make sure you have Node.js (v18+) and npm installed on your machine.

Node.js Download

Installation
Clone the Repository

git clone https://github.com/your-username/night-patrol-lookup.git
cd night-patrol-lookup
Setup Backend

cd server
npm install
Setup Frontend

cd ../client
npm install
🏃 Running the Application
1. Start the Backend API
cd server
npm start
The API server will start on http://localhost:3000

2. Start the Frontend Application
cd client
npm start
The React dev server will run on http://localhost:3001 (or next available port).

📡 API Reference
Get Record by ID
GET /lookup?id={RECORD_ID}
Query Parameters
Parameter

Type

Description

id

string

Required. The unique ID of the patrol record (e.g., NP-1001).

Response Example (200 OK)
{
  "success": true,
  "data": {
    "id": "NP-1001",
    "status": "ACTIVE",
    "type": "Patrol Shift",
    "location": "District A",
    "timestamp": "2026-11-04T09:53:00.000Z"
  }
}
Error Response Example (404 Not Found)
{
  "success": false,
  "error": "Record not found",
  "query": "NP-9999"
}
POST Request Alternative
POST /lookup
Content-Type: application/json

{
  "id": "NP-1001"
}
🛡️ Environment Variables & Security
For production deployments, consider creating a .env file in the server/ directory:

PORT=3000
NODE_ENV=production
ALLOWED_ORIGIN=https://your-frontend-domain.com
📄 License
Distributed under the MIT License. See LICENSE for more information.

