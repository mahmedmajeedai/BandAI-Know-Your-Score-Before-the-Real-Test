<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1b2a,40:1b4332,70:2d6a4f,100:40916c&height=220&section=header&text=BandAI&fontSize=76&fontColor=ffffff&fontAlignY=38&fontStyle=bold&desc=Know%20Your%20Score%20Before%20the%20Real%20Test.&descSize=18&descAlignY=62&descColor=b7e4c7" width="100%"/>

<br/>

<p align="center">
  <img src="https://img.shields.io/badge/Generative%20AI-Band%20Assessment-2d6a4f?style=for-the-badge&logo=openai&logoColor=white"/>
  <img src="https://img.shields.io/badge/NLP-Text%20Evaluation-40916c?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Full%20Stack-JS%20%2B%20HTML%20%2B%20CSS-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Modules-Listening%20%7C%20Reading%20%7C%20Writing%20%7C%20Speaking-2d6a4f?style=flat-square"/>
  <img src="https://img.shields.io/badge/Cost-100%25%20Free-brightgreen?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-GPL%203.0-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/Status-Beta%20Available-orange?style=flat-square"/>
</p>

<br/>

> **BandAI** is a free, AI-powered IELTS mock assessment platform that evaluates all four test modules — Listening, Reading, Writing, and Speaking — and returns a predicted band score using Generative AI and Natural Language Processing. No registration fees. No coaching centres. Just an honest score and actionable feedback.

<br/>

**[🎯 The Problem](#-the-problem) · [✨ Features](#-features) · [🏗️ Architecture](#️-system-architecture) · [🚀 Quickstart](#-quickstart) · [📁 Project Structure](#-project-structure) · [📄 Report](#-research-report)**

</div>

---

## 🎯 The Problem

Over three million students sit the IELTS exam every year. A large portion of them fail to achieve the band score required for university admission abroad — not because they lack ability, but because they had no reliable way to measure where they actually stand before test day.

Paid mock tests cost money. Coaching centres are expensive. And the handful of free tools online test only fragments of the exam — a few reading questions here, a vocabulary quiz there — without ever giving students a complete, scored assessment across all four modules.

**BandAI fills that gap entirely.**

It is the first free, AI-powered platform that conducts a full mock IELTS assessment across all four modules and returns a predicted band score — the same 1 to 9 scale used in the real exam — along with targeted feedback on where improvement is needed.

---

## ✨ Features

| Feature | Description |
|---|---|
| 📝 **Writing Assessment** | GenAI evaluates Task 1 and Task 2 responses on coherence, vocabulary, grammar, and task achievement |
| 🎙️ **Speaking Evaluation** | NLP analysis of spoken responses across fluency, pronunciation, lexical resource, and grammatical range |
| 👂 **Listening Module** | Timed listening exercises with automated answer validation and score calculation |
| 📖 **Reading Module** | Full reading passage with question sets and AI-graded responses |
| 🔢 **Band Score Prediction** | Weighted scoring across all four modules produces an overall predicted band on the 1-9 IELTS scale |
| 💬 **Actionable Feedback** | Module-level feedback identifies specific weak areas rather than just returning a number |
| 🆓 **Completely Free** | No subscription, no registration wall, no hidden cost of any kind |
| 🌐 **Web Interface** | Accessible from any browser with a full HTML/CSS/JS frontend |

---

## 🏗️ System Architecture

The swimlane diagram included in the repository (`IELTS Project Swimlane Diagram.pdf`) documents the full system flow. The high-level architecture is:

```
Student (Browser)
        │
        │  HTTP
        ▼
  Web Frontend (HTML + CSS + JS)
  ┌──────────────────────────────────────────┐
  │  Module selector  →  Test interface       │
  │  Answer input     →  Submission handler   │
  │  Results page     ←  Band score + feedback│
  └──────────────────────────────────────────┘
        │
        │  API calls
        ▼
  Python Backend (FastAPI / Jupyter)
  ┌──────────────────────────────────────────┐
  │                                           │
  │  Writing  →  GenAI evaluator             │
  │             (Task 1 + Task 2 scoring)    │
  │                                           │
  │  Speaking →  NLP pipeline               │
  │             (Speech features + scoring)  │
  │                                           │
  │  Reading  →  Answer comparison engine    │
  │                                           │
  │  Listening →  Audio + answer validator   │
  │                                           │
  │  Score Aggregator                         │
  │  Weighted average → Band 1-9 prediction  │
  └──────────────────────────────────────────┘
        │
        ▼
  Generative AI + NLP Models
  Language quality scoring, coherence
  analysis, vocabulary richness, grammar
```

---

## 📊 IELTS Band Scoring — How BandAI Evaluates

The real IELTS exam scores each module on four criteria. BandAI mirrors this structure using AI:

### Writing (Task 1 and Task 2)
| Criterion | What BandAI Checks |
|---|---|
| Task Achievement | Does the response address all parts of the prompt? |
| Coherence and Cohesion | Is the argument logically structured with appropriate linking? |
| Lexical Resource | Range and accuracy of vocabulary used |
| Grammatical Range and Accuracy | Variety and correctness of sentence structures |

### Speaking
| Criterion | What BandAI Checks |
|---|---|
| Fluency and Coherence | Natural flow, hesitation patterns, logical progression |
| Lexical Resource | Vocabulary range appropriate to the topic |
| Grammatical Range | Sentence variety and grammatical accuracy |
| Pronunciation | Clarity and intelligibility of speech |

### Reading and Listening
Objective scoring based on correct answers mapped to the official IELTS band conversion table.

---

## 📁 Project Structure

```
IELST-Band-Assessment-Tool/
│
├── project/                          Main application
│   ├── backend/                      Python evaluation engine
│   │   ├── writing_evaluator.py      GenAI writing scorer (Task 1 + Task 2)
│   │   ├── speaking_evaluator.py     NLP speech analysis pipeline
│   │   ├── reading_module.py         Passage and answer validation
│   │   ├── listening_module.py       Audio question and answer checker
│   │   └── band_calculator.py        Weighted score aggregation to band 1-9
│   │
│   └── frontend/                     Web interface
│       ├── index.html                Landing page and module selector
│       ├── style.css                 UI styling
│       └── app.js                   Test flow and API communication
│
├── beta/                             Beta version of the assessment tool
│
├── IELTS Project Swimlane Diagram.pdf  Full system flow documentation
├── Report ILETS Band Assessment Tool.pdf  Complete project research report
├── LICENSE                           GPL-3.0
└── README.md
```

---

## 🚀 Quickstart

### 1. Clone the repository

```bash
git clone https://github.com/mahmedmajeedai/IELST-Band-Assessment-Tool.git
cd IELST-Band-Assessment-Tool
```

### 2. Install dependencies

```bash
pip install -r project/requirements.txt
```

### 3. Set up your AI API key

BandAI uses a Generative AI model for Writing and Speaking evaluation. Add your key to the environment:

```bash
export OPENAI_API_KEY=your_key_here
# or configure in project/.env
```

### 4. Run the backend

```bash
cd project
python backend/app.py
```

### 5. Open the frontend

Open `project/frontend/index.html` in your browser or serve it locally:

```bash
python -m http.server 3000
```

Navigate to `http://localhost:3000` and start your mock test.

### 6. Try the beta version

```bash
cd beta
jupyter notebook
```

The beta version runs as a Jupyter notebook for rapid experimentation and scoring pipeline testing.

---

## 📄 Research Report

A full project report is included in the repository:

📘 **[Report ILETS Band Assessment Tool.pdf](./Report%20ILETS%20Band%20Assessment%20Tool.pdf)**

The report covers the problem statement, literature review, system design, implementation methodology, and evaluation results.

📊 **[IELTS Project Swimlane Diagram.pdf](./IELTS%20Project%20Swimlane%20Diagram.pdf)**

The swimlane diagram documents the complete data and control flow across all four modules from student input to band score output.

---

## 🌍 Who This Is For

| User | How BandAI Helps |
|---|---|
| 🎓 **Students applying abroad** | Get a realistic band prediction before registering for the real exam |
| 📚 **Self-study learners** | Identify exactly which module and criterion needs the most attention |
| 🏫 **Language institutes** | Offer students a free, AI-graded assessment tool alongside coaching |
| 🔬 **NLP researchers** | A reference implementation of multi-module language proficiency evaluation |

---

## 🤝 Contributing

Contributions are welcome. If you want to improve the scoring pipeline, add more question sets, or improve the frontend experience:

```bash
git checkout -b feature/your-improvement
git commit -m "feat: describe your change"
git push origin feature/your-improvement
```

Then open a Pull Request with a brief description of the change.

---

## 📄 License

This project is licensed under the **GNU General Public License v3.0**. See [LICENSE](LICENSE) for details.

---

<div align="center">

**Built by [Muhammad Ahmed Majeed](https://github.com/mahmedmajeedai)**

*Free IELTS band assessment for every student, everywhere.*

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:40916c,50:2d6a4f,100:0d1b2a&height=120&section=footer" width="100%"/>

</div>
