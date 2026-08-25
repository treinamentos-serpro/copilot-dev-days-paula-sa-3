🌐 [Português (BR)](README.pt_BR.md) | [Español](README.es.md)

<div align="center">

# 🎯 Soc Ops

**Break the ice. Fill the board. Shout "Bingo!"**

Soc Ops is a social bingo game for in-person mixers: every square is an icebreaker prompt, and you fill it by finding someone in the room who matches it. First to get 5 in a row wins — and everyone leaves knowing a few more people than they did before.

![Java](https://img.shields.io/badge/Java-21-orange?logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4-6DB33F?logo=springboot&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-3.9+-C71A36?logo=apachemaven&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue)

[🚀 Quick Start](#-quick-start) · [🎲 How to Play](#-how-to-play) · [📚 Lab Guide](#-lab-guide) · [🛠️ Tech Stack](#%EF%B8%8F-under-the-hood)

</div>

---

## 🎲 How to Play

1. **Open your board** — each player gets a randomized 5×5 grid of icebreaker prompts (the center square is a freebie ⭐).
2. **Work the room** — find people who match the prompts: *"has run a marathon"*, *"speaks three languages"*, *"has met a celebrity"*...
3. **Mark your squares** as you find your matches.
4. **Get 5 in a row** — horizontally, vertically, or diagonally — and you win! 🏆

Every board is freshly shuffled from the prompt catalog, so no two players are hunting for the same things.

## 🚀 Quick Start

All you need is [Java 21+](https://adoptium.net/) — the included Maven Wrapper handles the rest.

```bash
cd socops
./mvnw spring-boot:run
```

Then open **http://localhost:8080** and start mingling. 🎉

<details>
<summary><strong>More commands</strong></summary>

```bash
# Build a runnable JAR
cd socops
./mvnw clean package

# Run the test suite
./mvnw test
```

Prefer your own Maven? [Apache Maven 3.9+](https://maven.apache.org/) works too — just swap `./mvnw` for `mvn`.

</details>

## 📚 Lab Guide

This repo doubles as a hands-on **GitHub Copilot workshop**. Follow the guided labs to build features with AI agents:

| Part | Title | What you'll learn |
|------|-------|-------------------|
| [**00**](workshop/00-overview.md) | Overview & Checklist | The lay of the land |
| [**01**](workshop/01-setup.md) | Setup & Context Engineering | Give your AI the right context |
| [**02**](workshop/02-design.md) | Design-First Frontend | Iterate on UI with an agent |
| [**03**](workshop/03-quiz-master.md) | Custom Quiz Master | Build a custom agent |
| [**04**](workshop/04-multi-agent.md) | Multi-Agent Development | Orchestrate agents together |

📖 **[Start with the full Lab Guide →](workshop/GUIDE.md)** — also available offline in the [`workshop/`](workshop/) folder.

## 🛠️ Under the Hood

| Layer | Technology |
|-------|------------|
| Backend | Java 21 · Spring Boot 3.4 · Spring MVC |
| Frontend | Thymeleaf · vanilla JavaScript · CSS |
| Game state | `localStorage` in the browser — the server stays stateless |
| Build & quality | Maven Wrapper · Checkstyle · JUnit |

```
socops/src/main/java/com/socops/
├── web/       # HTTP wiring — pages & the fresh-board API
├── service/   # BoardAssembler: board creation, toggling, win detection
├── model/     # Domain types
└── data/      # The icebreaker prompt catalog
```

The site deploys automatically to **GitHub Pages** on every push to `main`.

## 🤝 Contributing

Found a bug or have a prompt idea? Check out the [Contributing Guide](CONTRIBUTING.md) and our [Code of Conduct](CODE_OF_CONDUCT.md).

---

<div align="center">

Made with ☕ and 🤖 for **GitHub Copilot Dev Days**

</div>
