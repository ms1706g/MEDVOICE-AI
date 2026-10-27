# Medivoice AI 

An AI-powered medical voice assistant that enables patients to communicate naturally through voice, analyzes symptoms using Large Language Models (LLMs), recommends the most suitable medical specialist, and generates structured consultation reports.

The application combines speech recognition, AI reasoning, text-to-speech, and real-time voice conversations to simulate an intelligent medical assistant.

---

## Live Demo

- **Frontend:** https://ai-medical-voice-agent-omega.vercel.app/

##  Features

-  User Authentication
-  Real-time AI Voice Conversation
-  Symptom Analysis
-  AI-powered Specialist Recommendation
-  Doctor Specialist Selection
-  Two-way Voice Communication
-  Automatic Medical Report Generation
-  MongoDB Database Integration
-  Stripe Subscription Integration
-  Download Consultation Reports (PDF)
-  Consultation History
-  Responsive Web Interface

---

# System Workflow

## User Flow

```text
User
   │
   ▼
Authentication ──► Dashboard ──► Start Consultation ──► Basic Information ──► Symptoms ──► Additional Details ──► AI Suggests Specialist ──► Select Doctor ──► Voice Conversation ──► Medical Report
```

---

# Architecture

The project consists of three major AI components.

```
Frontend (React)
        │
        ▼
Backend (Node.js + Express)
        │
        ▼
AI Services
├── VAPI.ai
│     ├── Speech-to-Text
│     ├── LLM
│     └── Text-to-Speech
│
├── AssemblyAI
│     └── Live Transcription
│
└── OpenAI
      └── Report Generation
```

---

# Voice Conversation Pipeline

```
User Speech → Speech-to-Text (Vapi.ai) → LLM Processing (OpenAI GPT-4o) → AI Response → Text-to-Speech (Vapi.ai) → Patient Hears Response → Live Transcription (AssemblyAI) → Conversation Stored (MongoDB) → Report Generator (OpenAI GPT-4o)

```

---

# AI Specialist Recommendation

Before starting the voice consultation, the user enters:

- Symptoms
- Additional Notes

The AI model analyzes the provided information and recommends the most appropriate medical specialist.

Example:

| Symptoms | Recommended Specialist |
|----------|------------------------|
| Chest Pain | Cardiologist |
| Skin Rash | Dermatologist |
| Eye Pain | Ophthalmologist |
| Headache | Neurologist |
| Stomach Pain | Gastroenterologist |

---

# AI Medical Report Generation

After the conversation ends, the transcript is processed by an LLM that generates a structured medical report.

The report includes:

- Session ID
- Patient Name
- Medical Specialist
- Timestamp
- Chief Complaint
- Conversation Summary
- Symptoms
- Duration
- Severity
- Medications Mentioned
- AI Recommendations

Example

```json
{
  "sessionId": "123456",
  "agent": "General Physician AI",
  "user": "John Doe",
  "timestamp": "2026-07-24T18:30:00Z",
  "chiefComplaint": "Persistent fever and sore throat",
  "summary": "The patient has experienced fever for three days along with sore throat and mild fatigue.",
  "symptoms": [
    "Fever",
    "Sore throat",
    "Fatigue"
  ],
  "duration": "3 days",
  "severity": "Moderate",
  "medicationsMentioned": [
    "Paracetamol"
  ],
  "recommendations": [
    "Stay hydrated",
    "Take adequate rest",
    "Consult a physician if symptoms worsen"
  ]
}
```

---

# Tech Stack

## Frontend

- React.js
- Tailwind CSS
- React Router
- Axios
- jsPDF

## Backend

- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT Authentication
- google oauth
- stripe

## AI & Voice

- OpenAI GPT
- VAPI.ai
- AssemblyAI
- Text-to-Speech
- Speech-to-Text

---

# Future Improvements

- Appointment Booking
- Multi-language Support
- AI Follow-up Consultations
- Doctor Dashboard
- Prescription Generation

