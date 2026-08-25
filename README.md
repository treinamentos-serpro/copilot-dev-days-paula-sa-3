<div align="center">

🌐 [Português (BR)](README.pt_BR.md) | [Español](README.es.md)

<br/>

# 🎱 Soc Ops

### Break the ice. Fill the board. Shout **"Bingo!"**

A social icebreaker bingo game for in-person mixers — built as a hands-on GitHub Copilot workshop.

[![Java 21](https://img.shields.io/badge/Java-21-orange?logo=openjdk&logoColor=white)](https://adoptium.net/)
[![Spring Boot 3.4](https://img.shields.io/badge/Spring%20Boot-3.4.2-brightgreen?logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Maven](https://img.shields.io/badge/Maven-Wrapper-blue?logo=apachemaven&logoColor=white)](https://maven.apache.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

[▶ Quick Start](#-quick-start) · [📚 Lab Guide](#-lab-guide) · [🏗 Architecture](#️-under-the-hood) · [🤝 Contributing](#-contributing)

</div>

---

## 🎮 How to Play

Each player gets a unique **5×5 bingo board** filled with icebreaker prompts. The center square is always free.

> **"Find someone who has traveled to another country this year!"**
> **"Find someone who speaks more than two languages!"**
> **"Find someone who has run a marathon!"**

Walk around the room, have conversations, and mark off squares when you find a match.
First to get **5 in a row** — horizontally, vertically, or diagonally — wins! 🏆

---

## ⚡ Quick Start

> **Requirement:** Java 21 JDK only — the Maven Wrapper is included, no separate Maven install needed.

```bash
# Clone and run
git clone https://github.com/treinamentos-serpro/copilot-dev-days-paula-sa-3.git
cd copilot-dev-days-paula-sa-3/socops
./mvnw spring-boot:run
```

Open **http://localhost:8080** and start the mixer! 🎉

<details>
<summary>Build & test commands</summary>

```bash
# Build a JAR
./mvnw clean package

# Run tests
./mvnw test
```

</details>

---

## 📚 Lab Guide

This repo is the playground for a **GitHub Copilot Dev Days** workshop. Each part teaches a specific Copilot skill using this app as the context.

| Part | Title | What you'll learn |
|------|-------|-------------------|
| [**00**](workshop/00-overview.md) | Overview & Checklist | Workshop goals, tools, and setup verification |
| [**01**](workshop/01-setup.md) | Setup & Context Engineering | Copilot instructions, `AGENTS.md`, prompt crafting |
| [**02**](workshop/02-design.md) | Design-First Frontend | AI-assisted UI design and Thymeleaf templating |
| [**03**](workshop/03-quiz-master.md) | Custom Quiz Master | Writing and deploying a custom Copilot agent |
| [**04**](workshop/04-multi-agent.md) | Multi-Agent Development | Orchestrating multiple agents on a shared codebase |

> 📝 All guides live in [`workshop/`](workshop/) for offline reading too.

---

## 🏗️ Under the Hood

| Layer | Technology |
|-------|-----------|
| Language | Java 21 |
| Framework | Spring Boot 3.4.2 · Spring MVC |
| Templates | Thymeleaf |
| Frontend | Vanilla JS · Custom CSS utilities |
| State | Stateless server — board state lives in `localStorage` |
| Deploy | GitHub Actions → GitHub Pages (`docs/`) |

```
socops/src/main/java/…/socops/
├── web/          # HTTP controllers (BingoRestController)
├── service/      # BoardAssembler — game logic, win detection
├── model/        # Domain types (Board, Cell, …)
└── data/         # IcebreakerPrompts catalog (24 fixed prompts)
```

---

## 🤝 Contributing

Spotted a bug or want to add a prompt? See [CONTRIBUTING.md](CONTRIBUTING.md) and [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).

---

<div align="center">

Made with ☕ for **GitHub Copilot Dev Days**

</div>
