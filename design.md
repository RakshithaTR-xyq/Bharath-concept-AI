Bharat Concept AI – System Design Document

1. System Overview

Bharat Concept AI uses a hybrid offline-first architecture combining Progressive Web App (PWA) technology, on-device AI, and cloud intelligence to deliver personalized conceptual learning for Bharat students.

The system prioritizes functionality in low-connectivity environments while enabling advanced AI support when internet is available.

---
2. High-Level Architecture

The system consists of three main layers:

Top Layer – User Interface
- Student Mobile Device
- PWA Frontend
- Voice Interaction Interface

Middle Layer – Core Intelligence
- Offline Lite AI Engine
- Learning Gap Detection Module
- Multilingual Processing Engine
- Brain Training Engine

Bottom Layer – Infrastructure
- Service Workers (Caching)
- Local Storage (IndexedDB)
- Sync Engine
- FastAPI Backend
- Cloud AI Models
- Cloud Storage

---

3. Technology Stack

Frontend
- Progressive Web App (React / Flutter Web)
- Service Workers
- IndexedDB

Backend
- FastAPI (Python)

AI Layer
- TensorFlow Lite / ONNX (offline models)
- PyTorch / Hugging Face (cloud models)
- Scikit-learn (gap detection)

Speech Processing
- Vosk (offline speech recognition)
- Coqui TTS / gTTS

Storage
- Local: IndexedDB / SQLite
- Cloud: Firebase / AWS S3

---

4. Offline-First Strategy

The system follows an offline-first approach:

1. Core app assets cached via service workers.
2. Lessons downloaded for offline access.
3. Lite AI model runs on-device.
4. User resources stored locally.
5. Background sync triggers when internet returns.

This ensures uninterrupted learning in low-connectivity regions.

---

5. AI Architecture

Offline Lite AI
Handles:
- word meanings
- basic explanations
- math tricks
- simple Q&A

Online Full AI
Handles:
- complex doubts
- deep explanations
- advanced personalization

Hybrid Decision Flow
1. User query received.
2. Offline AI attempts response.
3. If confidence low → route to cloud AI.
4. Response returned to user.

---

6. Data Flow

Student → PWA → Offline AI → Local Storage  
→ (if online) Sync Engine → FastAPI Backend → Cloud AI

---

7. Resource Upload Pipeline

1. User uploads file.
2. OCR extracts text (if image/PDF).
3. Content tagged by subject.
4. Stored locally.
5. Synced to cloud when online.

---
8. Scalability Considerations

- Modular AI components.
- Cloud auto-scaling backend.
- Language pack expansion.
- School-level deployment support.

---
9. Security Considerations

- HTTPS communication.
- Encrypted cloud storage.
- Local data sandboxing.
- Authentication for sync operations.

---

10. Future Improvements

- Personalized learning graphs.
- Emotion-aware tutoring.
- Teacher analytics dashboard.
- Federated learning for on-device improvement.
