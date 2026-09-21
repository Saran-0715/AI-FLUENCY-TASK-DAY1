# 🤖 AI Fluency Task – Day 1

> **Agentic AI: Foundations and Open-Source Practice**

A hands-on Python project demonstrating the difference between a **Plain LLM Chatbot**, **Rule-Based Workflow**, and **Tool-Using AI Agent** using a college course-fee assistant scenario.

## 📌 Project Overview

The project compares three approaches for answering college course-fee questions:

- 💬 **Chatbot** – Uses an LLM to generate responses.
- ⚙️ **Workflow** – Uses predefined Python rules and course-fee data.
- 🤖 **AI Agent** – Uses an LLM with tools for course-fee lookup and calculations.

### Course Data

| Course | Fee |
|---|---:|
| CS101 | ₹12,000 |
| AI202 | ₹18,000 |
| DS303 | ₹15,000 |

## 🛠️ Technologies

- Python
- Groq API
- GPT-OSS
- OpenAI-compatible API
- Python-dotenv
- Tool Calling
- Git & GitHub
- Visual Studio Code

## 📂 Project Structure

```text
AI-FLUENCY-TASK-DAY1/
│
├── agent.py
├── analysis.md
├── challenge.py
├── chatbot.py
├── check_setup.py
├── config.py
├── requirements.txt
├── tools.py
├── workflow.py
├── .gitignore
│
└── Output/
    ├── chatbot_output.png
    ├── workflow_output.png
    └── agent_output.png
```

## ⚙️ Setup

### 1. Clone the repository

```bash
git clone https://github.com/Saran-0715/AI-FLUENCY-TASK-DAY1.git
cd AI-FLUENCY-TASK-DAY1
```

### 2. Create virtual environment

```bash
python -m venv .venv
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure API Key

Create a `.env` file:

```text
PROVIDER=groq
GROQ_API_KEY=your_api_key_here
MODEL=openai/gpt-oss-120b
```

⚠️ **Never upload `.env` or your API key to GitHub.**

## ▶️ Run

```bash
python check_setup.py
python chatbot.py
python workflow.py
python agent.py
python challenge.py
```

## 📸 Output

Screenshots of the three systems are available in the `Output/` folder.

The project also includes `analysis.md`, which contains the detailed comparison and observations.

## 🔐 Security

Sensitive files are excluded using `.gitignore`:

```text
.env
.venv/
__pycache__/
```

## 👨‍💻 Author

**Saran Kumar T**

**B.Tech – Artificial Intelligence and Data Science (AIDS)**  
**Bannari Amman Institute of Technology**

---

⭐ *AI Fluency Task – Day 1 | Agentic AI Foundations*
