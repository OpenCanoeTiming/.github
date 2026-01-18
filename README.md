# Open Canoe Timing

Open-source timing solutions for canoe slalom races. Built by the community, for the community.

## About

Open Canoe Timing develops tools that work with **Canoe123** timing software to provide real-time scoreboards, data visualization, and race management utilities for canoe slalom competitions.

Our goal is to make professional-quality timing displays and tools accessible to clubs and race organizers of all sizes.

## Projects

### Core Applications

| Project | Description | Status |
|---------|-------------|--------|
| [c123-scoreboard](https://github.com/OpenCanoeTiming/c123-scoreboard) | Real-time scoreboard for live race display | Active |
| [c123-server](https://github.com/OpenCanoeTiming/c123-server) | WebSocket bridge between Canoe123 and web clients | Active |
| [c123-scoring](https://github.com/OpenCanoeTiming/c123-scoring) | Penalty entry and protocol verification app | In Development |

### Infrastructure

| Project | Description |
|---------|-------------|
| [timing-design-system](https://github.com/OpenCanoeTiming/timing-design-system) | Shared UI components and styles |
| [c123-xml-tools](https://github.com/OpenCanoeTiming/c123-xml-tools) | XML utilities for race data processing |
| [c123-protocol-docs](https://github.com/OpenCanoeTiming/c123-protocol-docs) | Protocol and XML format documentation |

## Architecture

```
┌─────────────────┐     TCP :27333     ┌─────────────────┐
│    Canoe123     │◄──────────────────►│   c123-server   │
│  (timing SW)    │                    │   :27123        │
└─────────────────┘                    └────────┬────────┘
                                                │
                              ┌─────────────────┼─────────────────┐
                              │ WebSocket /ws   │ REST API        │
                              ▼                 ▼                 ▼
                    ┌─────────────────┐ ┌─────────────────┐ ┌─────────────┐
                    │ c123-scoreboard │ │  c123-scoring   │ │ Admin UI    │
                    │   (display)     │ │  (penalties)    │ │ (config)    │
                    └─────────────────┘ └─────────────────┘ └─────────────┘
```

## Quick Start

### Running the Scoreboard

```bash
# 1. Start the server (connects to Canoe123)
cd c123-server
npm install && npm start

# 2. Start the scoreboard
cd c123-scoreboard
npm install && npm run dev
```

The scoreboard will be available at `http://localhost:5173` and automatically connects to `c123-server` on port 27123.

### Using the Design System

```bash
npm install @opencanoetiming/timing-design-system
```

```javascript
// Import CSS
import '@opencanoetiming/timing-design-system/css'

// Or use React components
import { Button, Card, Badge } from '@opencanoetiming/timing-design-system/react'
```

## Technology

- **Frontend:** React, TypeScript, Vite
- **Backend:** Node.js, WebSocket
- **Styling:** CSS with design tokens, dark/light themes
- **Protocol:** Canoe123 TCP/XML

## Contributing

We welcome contributions! Each project has its own `CONTRIBUTING.md` with specific guidelines.

- Report bugs and request features via GitHub Issues
- Submit pull requests with clear descriptions
- Follow existing code style and conventions

## Acknowledgements

This project would not exist without **[Canoe123](https://www.siwidata.com/)** - the professional timing system developed by **Siwidata**. Canoe123 is the backbone of canoe slalom timing at events worldwide, from local club races to World Championships.

We extend our gratitude to the Siwidata team for creating such a reliable and feature-rich timing solution, and for the protocol that makes these open-source extensions possible.

## License

All projects are released under the **MIT License** unless otherwise noted.

---

<sub>Built with ❤️ for the canoe slalom community</sub>
