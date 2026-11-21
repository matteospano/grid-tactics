# Grid Tactics

A pair of browser-based tactical prototypes for exploring turn-based combat systems, testing game rules, and evaluating human- and AI-assisted decision-making. Each project runs as a standalone HTML page and presents its mechanics through an interactive battlefield, deployment tools, and a combat log.

> **Project status:** Experimental mini-projects for simulation and play-testing. Game rules and balancing are subject to change.

## Projects

### Elemental Grid Tactics

A compact, turn-based tactical combat simulation built around elemental matchups and formation choices.

- Deploy five fighters on a 3×5 grid.
- Test a snake-order activation sequence, movement, and ranged attacks.
- Explore elemental strengths and weaknesses, front-line interception, and adjacency-based defense.
- Use promotion choices to adapt when a core elemental fighter is eliminated.
- Play against the built-in rule-based bot.

This project is suitable for testing how positioning, turn order, and combat modifiers interact. Its opponent is an in-game heuristic bot; it does not currently provide the external AI order-import workflow described below for the Roman tactics project.

### Roman Tactics: Teutoburg

A larger battlefield simulation focused on army deployment and simultaneous orders, using the Teutoburg ambush as its setting.

- Deploy two eight-unit armies on an 18×10 battlefield.
- Plan movement and attacks in WEGO-style rounds, then reveal and resolve both sides’ orders.
- Experiment with terrain effects, unit roles, cavalry charges, ranged volleys, collisions, and formation splits.
- Play against the built-in bot or use the 1-vs-1 mode.
- Export the current battlefield state and import AI-generated orders as editable suggestions.

#### AI-assisted scenario workflow

The AI integration is an **external, human-reviewed suggestion workflow**, not an autonomous in-game AI connection:

1. During the planning phase, use **Copy Field** to export the current army and battlefield state.
2. Provide that state to a tailored AI chat and request movement and attack orders for the scenario.
3. Paste the suggested orders using **Paste AI Orders**. The project applies them to the board as editable suggestions.
4. Review and adjust the orders in the simulation before confirming and resolving the round.

The precise AI prompt and scenario-specific instructions are forthcoming. Until those are published, treat AI output as experimental advice: check it against the current board, unit rules, and valid order format before execution. The simulation remains responsible for resolving the results.

## Run locally

No build step is required. Open either HTML file in a modern browser:

- `index.html` — Elemental Grid Tactics
- `imperivm_tactics_arena_command.html` — Roman Tactics: Teutoburg
- `teutoburg_ai_tactical_advisor_prompt` — Roman Tactics: Teutoburg AI prompt

The pages load Tailwind CSS and fonts from external CDNs, so an internet connection may be needed for the complete presentation.

## Purpose

These prototypes provide small, inspectable environments for experimenting with tactical rules and testing how structured AI suggestions can support scenario analysis. The Roman project’s export/import bridge is designed to keep the AI’s role bounded: it can propose orders from a supplied state, while a person reviews those orders and the game engine determines the outcome.
