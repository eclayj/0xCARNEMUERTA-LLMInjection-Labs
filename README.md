# 🧠 0xCARNEMUERTA: LLM Injection Labs

> Exploiting data. Securing AI. Living between the tokens and the dead prompts.

This is a security-aware lab for testing prompt injection vulnerabilities in large language models (LLMs) such as OpenAI’s `gpt-3.5-turbo` and `gpt-4`.

It is part of the personal AI + cybersecurity research portfolio of [@eclayj](https://github.com/eclayj), focused on identifying exploitable behavior in token-authenticated, prompt-driven interfaces.

---

## 📜 Phase 1: Prompt Injection Classifier

Run `llm_injection_lab_v1.py` to test predefined payloads and classify the model’s response behavior.

### ✅ Features

- Prompt injection attempts
- OpenAI SDK v1.x compatible
- Automatic classification
- Logging to `logs/logs.jsonl`

---

## 🧪 Quick Start

### 1. Install dependencies
```bash
pip install --upgrade openai
```

### 2. Set your OpenAI API key
```bash
set OPENAI_API_KEY=sk-proj-xxxxxxxxxxxxxxxxxxxx
```

### 3. Run the lab
```bash
python llm_injection_lab_v1.py
```

Results will be logged and classified in `logs/logs.jsonl`.

---

## 🧠 Classifier Tags

| Tag                  | Description                                                 |
|----------------------|-------------------------------------------------------------|
| `blocked`            | Model refused the injection                                 |
| `override_success`   | Model bypassed safety filters                               |
| `repeat_vulnerability` | Model echoed system or prompt content improperly          |
| `role_confusion`     | Model mistook user instructions for system-level authority  |
| `potential_bypass`   | Response was ambiguous or potentially vulnerable            |

---

## 📁 Repo Structure

```
├── llm_injection_lab_v1.py     # Main lab script
├── payloads/                   # Static and advanced prompt files
├── logs/                       # Auto-generated test logs
├── results/                    # Markdown summaries
└── tests/                      # Additional or chained GPT-4 tests
```

---

## 📎 Related Blog Post

🔗 [Prompt Injection: Dead Data and Exploitable AI](https://eclayj.github.io/0xcarnemuerta.github.io/2025/05/29/prompt-injection.html)

---

## 💠 GitHub Badge (for blog)

```markdown
[![View on GitHub](https://img.shields.io/badge/code-GitHub-blue?logo=github)](https://github.com/eclayj/0xCARNEMUERTA-LLMInjection-Labs)
```

---

## ⚠️ Disclaimer

This repository is for educational and research purposes only.  
Do not use these techniques against production systems you do not own.
