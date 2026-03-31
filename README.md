# Signable — ASL Learning Platform

> A cross-platform web application for learning American Sign Language, built with Ionic/React and Firebase. Live at **[signable-dev.web.app](https://signable-dev.web.app/welcome)**

---

## About

Signable is a supplemental learning tool for students and self-learners studying American Sign Language. It combines interactive study tools, a real-time sign lookup API, and a custom-trained machine learning model that recognizes ASL hand signs through your camera — giving learners instant, accurate feedback as they practice.

The app has been piloted in a classroom setting and is actively being developed toward full mobile support and movement-based sign recognition.

---

## My Role

**Co-Founder & Full Stack Developer** — Team of 5 (4 engineers, 1 designer)

I was responsible for the core technical architecture of the application, including:

- **App architecture & project setup** — Designed and scaffolded the full Ionic/React application structure, configured Firebase project, and established development conventions for the team
- **Firebase backend** — Set up Firestore database schema, Firebase Authentication for user accounts, and Firebase Storage for user data persistence
- **CI/CD pipeline** — Configured continuous deployment via Firebase Hosting, enabling automatic deploys on merge to main
- **Sign recognition system** — Trained and integrated a Random Forest classifier on a custom ASL alphabet dataset; built the full pipeline from webcam input → hand landmark extraction → model inference → real-time user feedback
- **ASL-Lex API integration** — Integrated the ASL-Lex research API to power the sign dictionary feature; users can look up any word and receive video demonstrations by professional ASL researchers along with related signs
- **Flashcard system & frontend** — Built core learning features including dynamic flashcards and contributed to overall UI implementation

---

## Features

### ✋ Sign Recognition (ML-Powered)
Practice ASL letters and get real-time feedback through your camera. A custom-trained Random Forest model analyzes hand landmarks and tells you whether your sign is correct.

- Custom dataset, trained from scratch
- Recognizes the full ASL alphabet (static signs)
- Instant in-browser inference — no server round trip

### 📖 ASL-Lex Dictionary
Look up any word and see how it's signed — powered by the ASL-Lex API, a database built by ASL researchers at the University of Rochester.

- Video demonstrations by professional ASL signers
- Related signs and variants surfaced automatically
- Searchable from anywhere in the app

### 🃏 Flashcards & Quiz Mode
Reinforce learning through spaced repetition-style flashcard decks and quiz modes covering the ASL alphabet and vocabulary.

### 👤 User Accounts & Progress Tracking
Firebase Authentication keeps users signed in across sessions. Firestore persists study notes and individual progress metrics so learners can pick up where they left off.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | Ionic + React |
| Language | TypeScript / JavaScript |
| Backend | Firebase (Firestore, Auth, Storage, Hosting) |
| ML Model | Random Forest (custom-trained, ASL alphabet dataset) |
| Hand Tracking | OpenCV / MediaPipe (landmark extraction pipeline) |
| External API | ASL-Lex Research API |
| CI/CD | Firebase Hosting (auto-deploy on merge) |

---

## Architecture Overview

```
┌─────────────────────────────────────────────┐
│              Ionic/React Frontend            │
│   Flashcards │ Quiz │ Dictionary │ Camera   │
└────────────────────┬────────────────────────┘
                     │
         ┌───────────┴───────────┐
         │                       │
┌────────▼────────┐   ┌─────────▼──────────┐
│  Firebase Suite │   │   ASL-Lex API      │
│  Firestore      │   │   Sign videos +    │
│  Auth           │   │   related signs    │
│  Storage        │   └────────────────────┘
│  Hosting        │
└────────┬────────┘
         │
┌────────▼──────────────────────┐
│     Sign Recognition Pipeline │
│                               │
│  Webcam → MediaPipe Landmarks │
│  → Random Forest Classifier   │
│  → Real-time Feedback UI      │
└───────────────────────────────┘
```

---

## Roadmap

The following features are actively in development:

- **Mobile app** — Rebuilding for native iOS and Android via Ionic's mobile pipeline
- **Movement sign recognition** — Extending the ML pipeline beyond static letter signs to recognize signs that involve motion (the majority of ASL vocabulary)
- **Community discussion board** — A space for learners to ask questions and engage with the ASL community

---

## Note on Repository

Signable is a collaborative project. The full source repository is maintained by the team at the link **[here](https://github.com/BryanAyala123/signable)**. This repo serves as a showcase of my personal contributions and technical decisions on the project.

For a live demo, visit **[signable-dev.web.app](https://signable-dev.web.app/welcome)**

---

*Signable is an ongoing project. Last updated 2026.*
