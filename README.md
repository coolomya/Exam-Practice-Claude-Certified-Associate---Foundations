# Claude Certified Associate – Foundations Practice Exam

A lightweight, browser-based practice exam simulator inspired by the **Claude Certified Associate – Foundations (CCAO-F)** certification exam.

The project provides a realistic exam-style interface with timed questions, navigation, review marking, answer tracking, and a final results/review screen.

> **Disclaimer:** This is an independent practice tool and is not affiliated with, endorsed by, or provided by Anthropic.

---

## ✨ Features

* ⏱️ **120-minute exam timer**
* 📝 Multiple-choice practice questions
* 🔘 Support for single-answer and multiple-answer questions
* 🧭 Previous / Next question navigation
* 🔢 Question navigation palette
* 🚩 Mark questions for review
* 📊 Visual indication of:

  * Current question
  * Answered questions
  * Questions marked for review
  * Unanswered questions
* ⚠️ Confirmation before submitting with unanswered questions
* ⏰ Automatic submission when the timer expires
* 📋 Detailed answer review after submission
* 🔄 Restart exam functionality
* 📱 Responsive layout for desktop and mobile
* 📂 Load questions from an external `quiz_data.json`
* 📤 Manual JSON file upload as a fallback
* 🛡️ HTML escaping for dynamically loaded question content
* 🚫 No backend required

---

## 📚 Topics Covered

The practice questions are designed around foundational concepts related to Claude, Generative AI, LLMs, and AI infrastructure.

Current question sets include topics such as:

### Generative AI

* What Generative AI is
* How generative models produce content
* AI vs Machine Learning vs Generative AI
* Training vs inference

### LLMs

* What Large Language Models are
* How LLMs generate responses
* Autoregressive next-token prediction
* Tokens and tokenization
* Input and output tokens
* Context windows
* Model parameters and weights

### LLM vs SLM

* Large Language Models
* Small Language Models
* Capability vs resource requirements
* Cloud vs local/edge use cases

### Claude Models

Understanding the general positioning of Claude model families:

| Model family | General positioning                    |
| ------------ | -------------------------------------- |
| **Haiku**    | Speed and cost efficiency              |
| **Sonnet**   | Balance of capability, speed, and cost |
| **Opus**     | Highest capability for demanding tasks |

The exact model lineup and pricing can change over time, so the practice material focuses primarily on **model-selection principles** rather than treating a particular model/version as permanently superior.

### Token Pricing

* What a token is
* Input vs output tokens
* Token-based pricing
* Cost calculation
* Why longer prompts/responses can cost more

### Computer Hardware

Basic concepts involving:

* CPU
* GPU
* RAM
* ROM / persistent storage
* VRAM
* Why GPUs are commonly used for AI workloads
* Model weights and GPU memory

### AI Infrastructure

* Where hosted LLMs run
* Inference servers
* GPUs and AI accelerators
* Electricity consumption
* Heat generation
* Data-center cooling
* Water usage in some cooling systems

### End-to-End LLM Request

The practice material also covers the basic flow:

```text
User
  │
  ▼
Application
  │
  ▼
LLM API / Model Server
  │
  ▼
Tokenization
  │
  ▼
Model Inference
  │
  ▼
Next-token generation
  │
  ▼
Generated Tokens
  │
  ▼
Detokenization
  │
  ▼
Response
```

---

## 📁 Project Structure

```text
.
├── index.html
├── quiz_data.json
└── README.md
```

Depending on the version of the project, the HTML file may have a different name, for example:

```text
ccao-f-practice-exam.html
```

---

## 🚀 Running Locally

The simulator is designed to work without a backend.

### Option 1 – Open directly

Download or clone the repository and open the HTML file in your browser.

```bash
git clone <your-repository-url>
cd <repository-folder>
```

Then open:

```text
ccao-f-practice-exam.html
```

### Option 2 – Run a local HTTP server

Running through a local server is recommended because the application can automatically load `quiz_data.json`.

With Python:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

---

## 🧩 Question Data Format

Questions are stored in `quiz_data.json`.

Example:

```json
[
  {
    "id": 1,
    "domain": "Generative AI Fundamentals",
    "question": "What is Generative AI?",
    "options": [
      "A system that only stores information",
      "AI that can generate new content",
      "A database management system",
      "A computer operating system"
    ],
    "answer": 1
  }
]
```

The `answer` field represents the correct option index.

For example:

```json
"answer": 1
```

means the second option is correct because arrays are zero-indexed.

---

## 📝 Adding Questions

To add more questions, edit `quiz_data.json`.

Example:

```json
{
  "id": 21,
  "domain": "LLM Fundamentals",
  "question": "What does an LLM typically generate during autoregressive inference?",
  "options": [
    "The next token",
    "A new CPU instruction",
    "A database table",
    "A GPU driver"
  ],
  "answer": 0
}
```

Then refresh the browser.

---

## 🎯 Intended Use

This project is intended for:

* Personal CCAO-F preparation
* Learning foundational Generative AI concepts
* Understanding LLM terminology
* Practicing model-selection questions
* Learning basic AI infrastructure concepts
* Building familiarity with timed multiple-choice exams

It can also serve as a starting point for creating practice simulators for other technical certifications.

---

## 🧠 Exam Simulation

The simulator follows an exam-style workflow:

```text
Start Exam
    │
    ▼
Question 1
    │
    ├── Answer
    ├── Mark for Review
    └── Navigate
          │
          ▼
      Next Question
          │
          ▼
      ...
          │
          ▼
     Submit Exam
          │
          ▼
     Calculate Score
          │
          ▼
    Review Answers
```

The timer automatically submits the exam when it reaches zero.

---

## 📊 Score Calculation

The simulator displays a **raw percentage score** based on the number of correctly answered questions.

For example:

```text
Correct: 16
Total:   20

Score: 80%
```

The displayed percentage should **not** be interpreted as an official Anthropic certification score or passing threshold.

Official certification scoring may use its own scoring methodology.

---

## ⚠️ Disclaimer

This project is an **unofficial practice tool**.

It is not:

* An official Anthropic exam
* An official CCAO-F question bank
* A copy of the actual certification examination
* Affiliated with Anthropic
* A guarantee of certification success

Questions are intended for educational and practice purposes.

---

## 🔮 Possible Future Improvements

Potential improvements include:

* [ ] Larger question bank
* [ ] Randomized question order
* [ ] Randomized answer order
* [ ] Question categories / domain filtering
* [ ] Difficulty levels
* [ ] Explanations for every answer
* [ ] Score history
* [ ] Weak-topic analysis
* [ ] Practice mode without a timer
* [ ] Full exam mode
* [ ] Configurable exam duration
* [ ] Import/export question banks
* [ ] Dark mode
* [ ] Keyboard shortcuts
* [ ] Progress persistence using `localStorage`
* [ ] PWA/offline support
* [ ] More realistic exam statistics

---

## 🛠️ Technologies

This project intentionally keeps the stack simple.

```text
HTML
CSS
JavaScript
JSON
```

No backend or database is required.

---

## 📜 License

This project is intended for personal educational and practice use.
