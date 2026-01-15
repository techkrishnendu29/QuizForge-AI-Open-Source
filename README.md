# QuizForge AI
**QuizForge AI** is an open-source Android + AIML project that generates **topic-wise practice questions** (MCQs + Short Q/A) for students using a lightweight NLP-based pipeline. It is designed to be **open-source friendly**, easy to contribute to, and scalable from **offline generation** to **LLM-enhanced generation**.

> Tagline: *Turn any topic into a quiz — instantly.*

---

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Screenshots](#screenshots)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Project Structure](#project-structure)
- [Quick Start](#quick-start)
- [How It Works (AI Pipeline)](#how-it-works-ai-pipeline)
- [Datasets / Question Packs](#datasets--question-packs)
- [Roadmap](#roadmap)
- [Governance](#governance)
- [Contributing](#contributing)
- [License](#license)

---

## Overview
Students often waste time searching for quality practice questions. **QuizForge AI** solves this by generating quizzes from a topic name using:
- **Curated question banks** (JSON packs)
- **Keyword matching + template generation**
- Optional future upgrade: **LLM integration**

The project is maintained as a **community-driven open-source repository** where contributors can add topics, questions, UI features, and ML improvements.

---

## Features
### Student Features
- Topic-based quiz generation (OS/DBMS/AIML/DSA)
- MCQ mode, Short Answer mode, or Mixed mode
- Difficulty selection: Easy / Medium / Hard
- Scorecard + explanations (for MCQ)
- Quiz history
- Bookmark/save questions
- Revision mode (repeat wrong/saved questions)

### Open Source Features
- Topic packs via simple JSON
- Modular generator pipeline
- Beginner-friendly contribution tasks

---

## Screenshots
> Add screenshots here (place images inside `/docs/screenshots/`)
- Home
- Quiz
- Results
- History

---

## Tech Stack
- **Android:** Kotlin
- **UI:** Material 3
- **Architecture:** MVVM + Clean Architecture
- **Local DB:** Room
- **JSON:** Gson/Moshi
- **NLP:** TF-IDF/RAKE + template-based generation
- **CI/CD:** GitHub Actions

---

## Architecture
QuizForge AI uses a clean modular architecture:
- `presentation/` → UI + ViewModels
- `domain/` → Use-cases + core interfaces
- `data/` → Room + JSON loaders + repositories
- `generator/` → AI/NLP generation pipeline

---

## Project Structure
```
QuizForgeAI/
├── android-app/
├── docs/
│   ├── screenshots/
│   └── architecture/
├── .github/
│   ├── ISSUE_TEMPLATE/
│   └── PULL_REQUEST_TEMPLATE.md
├── ROADMAP.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── SECURITY.md
├── LICENSE
└── README.md
```

---

## Quick Start
### Requirements
- Android Studio (latest stable)
- Kotlin
- Android SDK 24+

### Run Locally
```bash
git clone https://github.com/<your-username>/QuizForgeAI.git
cd QuizForgeAI
```
Open `android-app/` in Android Studio → Sync Gradle → Run.

---

## How It Works (AI Pipeline)
1. User enters a topic (e.g., **CPU Scheduling**)
2. App extracts keywords from the topic
3. It loads matching question packs (JSON)
4. Generates quiz by selecting questions by topic + difficulty
5. Results are scored and stored in Room DB

---

## Datasets / Question Packs
Question packs are stored as JSON inside:
`android-app/app/src/main/assets/question_bank/`

### JSON format example
```json
{
  "topic": "CPU Scheduling",
  "keywords": ["fcfs", "sjf", "round robin", "waiting time"],
  "mcq": [
    {
      "question": "Which scheduling algorithm is non-preemptive?",
      "options": ["Round Robin", "FCFS", "Priority (Preemptive)", "SRTF"],
      "answerIndex": 1,
      "difficulty": "easy",
      "explanation": "FCFS is non-preemptive."
    }
  ],
  "short": [
    {
      "question": "Define turnaround time.",
      "answer": "Turnaround time is total time from submission to completion."
    }
  ]
}
```

---

## Roadmap
See [ROADMAP.md](ROADMAP.md).

---

## Governance
### Maintainer / Project Admin
- **Project Admin:** Your Name
- Response SLA:
  - Issues: 24–48 hrs
  - PR Review: 48–72 hrs

### Decision Making
- The admin approves major changes.
- Community feedback is considered via discussions and issues.

---

## Contributing
Contributions are welcome.
- Read: [CONTRIBUTING.md](CONTRIBUTING.md)
- Start with issues labeled **good first issue**

---

## License
This project is licensed under the **MIT License**. See [LICENSE](LICENSE).
