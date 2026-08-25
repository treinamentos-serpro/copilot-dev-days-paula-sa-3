# Repository Guide for AI Agents

## Mandatory development checklist

- [ ] Lint: no lint command is configured; manually review changed JavaScript/CSS/Java.
- [ ] Build: `cd socops && ./mvnw clean package`
- [ ] Test: `cd socops && ./mvnw test`

## Project shape

- `socops/` is Java 21, Spring Boot 3.4.2, Spring MVC, Thymeleaf, and vanilla JavaScript.
- `SocOpsApplication` starts the app. `BingoRestController` serves `game` at `/` and fresh boards at `GET /api/bingo/fresh-board`.
- `BoardAssembler` is static, Spring-free game logic for board creation, toggling, and win detection. Cover changes with focused tests in `socops/src/test/`.
- `model/` holds the domain contract; `data/IcebreakerPrompts` holds fixed prompts. `game.html` stores browser state in `localStorage`; the server has no game session.

## Game invariants

- Boards are 5x5 with 25 zero-based IDs; cell `12` is a free, preselected, untoggleable center.
- Board generation shuffles the fixed catalog and selects 24 unique prompts.
- Winning lines are checked in order: rows, columns, main diagonal, anti-diagonal.
- Cell updates preserve copy-on-write behavior.

## Change guidance

- Keep HTTP wiring in `web/`, domain types in `model/`, fixed data in `data/`, and rules in `BoardAssembler`.
- For UI work, follow [app.css](socops/src/main/resources/static/css/app.css), [CSS guidance](.github/instructions/css-utilities.instructions.md), and [frontend guidance](.github/instructions/frontend-design.instructions.md).
- Use [README.pt_BR.md](README.pt_BR.md) for setup. Link to relevant workshop pages rather than duplicating instructional content.
- The default port is `8080`. The deploy workflow publishes `docs/` to GitHub Pages, not the Spring Boot app; see [.github/workflows/deploy.yml](.github/workflows/deploy.yml).