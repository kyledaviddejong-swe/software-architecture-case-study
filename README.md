# Multiplayer Game · Architecture Study

A software design case study for taking **Draw It or Lose It**, an Android game in a fictional client scenario, to a browser-based multiplayer service. It demonstrates requirements analysis, object-oriented modeling, platform evaluation, and reasoning about shared state.

**Read the [design report (PDF)](docs/software-architecture-report.pdf)** · [Editable Word version](docs/software-architecture-report.docx)

## What this project covers

- Multiple teams and players sharing a game session, with unique names and server-controlled game state.
- The relationship between `GameService`, `Game`, `Team`, `Player`, and the shared `Entity` base class.
- Tradeoffs across Linux, macOS, Windows, and mobile devices for hosting, browser access, and development.
- Recommendations for storage, memory, networking, and access control.

The proposed design separates browser interaction from authoritative game logic and shared persistence. A Linux server is the recommended starting point. An in-process singleton can organize one application instance, but coordinating multiple server processes requires additional shared-state and concurrency mechanisms.

## My contribution

I interpreted the user's needs as constraints that shaped the design, then connected the architectural decisions back to those requirements. Scalability and consistency were central concerns: multiple teams must be able to play without clients independently controlling shared state. The report explains the domain model and evaluates how the operating environment affects that design.

Working through the design before implementation made the responsibilities and boundaries easier to identify. A technically correct system that ignores operational realities can still fail in practice. The report connects that overview to domain responsibilities and platform tradeoffs.

## Scope and background

An undergraduate design case study based on a supplied fictional client scenario and domain model. The repository contains the design report; no application implementation is included.

See [credits and acknowledgments](CREDITS.md). Technical references are included in the report.
