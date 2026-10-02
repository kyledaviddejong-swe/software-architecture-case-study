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

Working through the design before implementation made the responsibilities and boundaries easier to identify. A technically correct system that ignores operational realities can still fail in practice. The portfolio edition adds a concise architecture overview and clarifies where a design recommendation still needs implementation and testing.

## Scope

This is a **documentation case study**, not a runnable game or deployed service. No application source is included in this repository, and no runtime, performance, or security testing is claimed. The PDF is the quickest way to review the work; no development setup is required.

## Academic context and cleanup

Prepared for SNHU CS-230 using the supplied fictional Gaming Room scenario and domain model. My contribution here is the written analysis and recommendations; the scenario and class structure are not presented as an independently invented product. This is not a real client engagement.

The portfolio edition removes template instructions and supplied artwork, reorganizes the dense platform comparison, and corrects overbroad claims about singleton scope, shared state, session isolation, and platform compatibility. The original UML graphic is omitted because its authorship and redistribution status have not been established. AI assistance was used for this portfolio cleanup. The original school submission is preserved separately.

Technical references used for the cleanup: [PostgreSQL constraints](https://www.postgresql.org/docs/18/ddl-constraints.html) and [Visual Studio Code platform support](https://code.visualstudio.com/docs/supporting/faq). These support specific explanations, not claims of an implemented database or toolchain.
