Deskflow readme · MD
Copy

# DeskFlow

> **TL;DR:** DeskFlow is a desktop productivity and automation application built with **Python and JavaScript** to help users manage tasks and eliminate repetitive workflows. It includes a **task timer with active/idle time detection, a Quick Delete feature for instant file cleanup, and an AI email assistant powered by OpenAI GPT that can summarize threads, prioritize messages, and help draft replies.** The project strengthened my skills in **desktop app development, automation design, system activity monitoring, and integrating AI-powered productivity tools.**

---

## 💡 Inspiration

In today's fast-paced digital environment, users face increasing pressure to manage repetitive and time-consuming tasks — file organization, scheduling, communication — often across multiple disconnected tools. DeskFlow was built to consolidate these into a single, intelligent desktop application that gives users back control over their time.

---

## ✨ Features

### ✅ Implemented

- **Task Timer** — tracks active and idle time to help users monitor productivity sessions
- **Quick Delete** — instant file cleanup tool for removing files without navigating file explorers
- **AI Email Assistant** — powered by OpenAI GPT; summarizes email threads, prioritizes messages by urgency, and assists with drafting replies

### 🔧 In Progress

- **File Organizer** — automated sorting of files into folders by type, date, or custom rules

---

## 🏗️ Architecture

DeskFlow follows a **desktop application architecture** with a Python backend handling system-level operations and automation logic, and a JavaScript frontend managing the UI layer.

```
┌─────────────────────────────────────────┐
│           JavaScript Frontend           │
│         (UI, Dashboard, Controls)       │
└─────────────────┬───────────────────────┘
                  │  IPC / API calls
                  ▼
┌─────────────────────────────────────────┐
│           Python Backend                │
│  ┌─────────────┐   ┌─────────────────┐  │
│  │ Task Timer  │   │  Quick Delete   │  │
│  │ (activity   │   │  (file system   │  │
│  │  monitoring)│   │   operations)   │  │
│  └─────────────┘   └─────────────────┘  │
│  ┌──────────────────────────────────┐   │
│  │       AI Email Assistant         │   │
│  │  (OpenAI GPT API integration)    │   │
│  └──────────────────────────────────┘   │
└─────────────────────────────────────────┘
                  │
                  ▼
        ┌──────────────────┐
        │   OpenAI API     │
        │  (GPT — email    │
        │   summarization, │
        │   prioritization,│
        │   reply drafting)│
        └──────────────────┘
```

**Key design decisions:**
- Python handles all system-level operations (file I/O, activity monitoring, process management) where it has the strongest native support
- The AI email assistant makes calls to the OpenAI API, passing email content and returning structured summaries and draft responses
- The frontend communicates with the Python layer to trigger automation actions and display results in real time

---

## 🤖 AI Email Assistant

The email assistant is integrated with the **OpenAI GPT API** and supports three core functions:

- **Summarize** — condenses long email threads into a short, readable summary
- **Prioritize** — analyses message content and flags high-urgency emails
- **Draft replies** — generates context-aware reply suggestions based on the thread

All prompts are structured to return clean, actionable output directly usable within the app.

---

## 🖥️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | JavaScript |
| Backend | Python |
| AI Integration | OpenAI GPT API |
| Runtime | Node.js |

---

## 🚀 Getting Started

**1. Clone the repository**
```bash
git clone https://github.com/yourusername/deskflow.git
cd deskflow
```

**2. Install dependencies**
```bash
npm install
```

**3. Set up environment variables**

Create a `.env` file in the root directory:
```env
OPENAI_API_KEY=your_openai_api_key_here
```

**4. Start the application**
```bash
npm start
```

---

## 👥 Target Users

- **Office Professionals** — managing files, scheduling, and high email volumes
- **Freelancers & Remote Workers** — automating admin tasks to stay focused on billable work
- **Students & Academics** — handling large volumes of documents and deadlines
- **IT & Data Entry Staff** — dealing with repetitive, structured tasks daily

---

## 🛠 Future Improvements

- [ ] Complete File Organizer — automated sorting by type, date, or custom rules
- [ ] Containerise with Docker for easier cross-platform distribution
- [ ] Calendar and scheduling integration
- [ ] Subscription/licensing model for premium features
- [ ] Expanded AI features — smart scheduling suggestions, meeting prep summaries

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Submit a pull request
