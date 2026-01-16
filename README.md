# 🚀 Agent Zero on Docker (Docker Compose Setup)

**Author:** Amjid Ali
**Role:** CIO | AI & Automation Specialist | Educator
**Website / LMS:** [https://lms.syncbricks.com](https://lms.syncbricks.com)
**YouTube Channel:** [https://youtube.com/syncbricks](https://youtube.com/syncbricks)

---

## 📌 Overview

This repository provides a **production-ready Docker Compose setup** to run **Agent Zero** locally or on a server using Docker.

Agent Zero is a powerful autonomous AI agent framework that can be used for:

* AI task automation
* Research agents
* Workflow orchestration
* Tool-using agents
* AI experimentation and learning

This setup is **simple, stable, and beginner-friendly**, while still suitable for advanced users.

---

## 🧠 Who Is This For?

This guide is ideal for:

* Developers learning **AI agents**
* Professionals exploring **automation & agent-based systems**
* Students following **hands-on AI tutorials**
* Anyone using **Docker, n8n, or local AI tools**

If you’re learning **Docker, n8n, AI agents, or automation**, step-by-step tutorials are available on:

👉 **[https://lms.syncbricks.com](https://lms.syncbricks.com)**
👉 **[https://youtube.com/syncbricks](https://youtube.com/syncbricks)**

---

## 🧰 Prerequisites

Make sure you have:

* Docker **20.10+**
* Docker Compose **v2**
* An OpenAI-compatible API key (OpenAI / Azure / local LLMs)
* Basic Docker knowledge (covered in my courses)

---

## 📁 Folder Structure

```text
agent-zero/
├── docker-compose.yml
├── .env
└── data/
```

The `data` folder is used for **persistent agent memory**.

---

## 🔐 Environment Configuration

Create a `.env` file:

```env
OPENAI_API_KEY=your_api_key_here
OPENAI_BASE_URL=https://api.openai.com/v1
OPENAI_MODEL=gpt-4o-mini

TZ=Australia/Sydney
AGENT_ZERO_DATA_DIR=/data
```

---

## 🐳 Docker Compose Configuration

Below is the **recommended Docker Compose setup** for Agent Zero:

```yaml
version: "3.9"

services:
  agent-zero:
    image: frdel/agent-zero:latest
    container_name: agent-zero
    restart: unless-stopped

    ports:
      - "5000:80"

    env_file:
      - .env

    volumes:
      - ./data:/data

    tty: true
    stdin_open: true
```

---

## ▶️ Start Agent Zero

Run:

```bash
docker compose up -d
```

Check logs:

```bash
docker logs -f agent-zero
```

---

## 🌐 Access the Web UI

Open your browser:

```
http://localhost:5000
```

You should now see the **Agent Zero Web Interface** running successfully.

---

## 🔒 Security Tip (Recommended)

If running on a server or VPS, restrict access to localhost only:

```yaml
ports:
  - "127.0.0.1:5000:80"
```

Then expose it safely via:

* Reverse proxy (nginx / traefik)
* Cloudflare Tunnel
* VPN

These setups are covered in my tutorials.

---

## 🔗 Integration Ideas

Agent Zero works very well alongside:

* **n8n** (workflow automation)
* **Qdrant** (vector database)
* **Ollama** (local LLMs)
* **Cloudflare Tunnels**
* **PostgreSQL**

Practical integrations are demonstrated on my **YouTube channel** and **LMS**.

---

## 🎓 Learn More (Free & Paid Tutorials)

If you want **hands-on, real-world learning**, check out:

### 📘 LMS (Structured Courses)

👉 **[https://lms.syncbricks.com](https://lms.syncbricks.com)**

Courses include:

* Docker for Automation
* n8n Workflow Automation
* AI Agents & Agent Zero
* Self-hosting AI tools
* Real enterprise automation use cases

### 🎥 YouTube (Free Tutorials)

👉 **[https://youtube.com/syncbricks](https://youtube.com/syncbricks)**

You’ll find tutorials on:

* Docker & Docker Compose
* n8n automation
* Agent Zero
* AI tools & integrations
* Practical DevOps setups

---

## 👤 About the Author

**Amjid Ali** is a CIO, AI & Automation Expert, and educator with over two decades of experience in:

* Enterprise IT & Infrastructure
* Workflow automation
* AI systems & agents
* Low-code platforms
* Real-world production deployments

This repository reflects **practical, tested setups** used in real projects and teaching environments.

---

## ⭐ Support & Community

If this helped you:

* ⭐ Star the repository
* 📺 Subscribe on YouTube
* 🎓 Join the courses on SyncBricks LMS

Happy building 🚀
**– Amjid Ali**
