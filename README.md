# try-agui

Experimental repository for exploring the [AG-UI](http://docs.ag-ui.com/introduction) framework.

## About AG-UI

AG-UI is an open protocol that standardizes how front-end applications connect to AI agents. It provides:

- **Real-time interactivity** with AI agents
- **Live state streaming** for dynamic updates
- **Human-in-the-loop collaboration** workflows
- **Transport-agnostic** communication (SSE, webhooks, WebSockets)

### Key Features

- Lightweight and minimally opinionated
- Event-driven bidirectional communication
- Support for multiple agent frameworks (LangGraph, CrewAI, etc.)
- Focus on agent-user interaction layer
- Complementary to A2A (agent-to-agent) and MCP (model context protocol)

## Setup

This project uses [uv](https://docs.astral.sh/uv/) for Python package management.

### Prerequisites

- Python >=3.12
- [uv](https://docs.astral.sh/uv/getting-started/installation/) installed

### Installation

```bash
# Install dependencies
uv sync

# Run the example script
uv run python hello.py
```

## Getting Started

Visit the [AG-UI documentation](http://docs.ag-ui.com/introduction) for detailed guides and examples.

## Projects

### CLI Agent (`my-ag-ui-cli-app/`)

A working CLI application demonstrating AG-UI integration with:
- Real-time streaming agent responses
- Weather API tool integration
- Web browser launching capability
- Persistent memory with LibSQL
- Built with Mastra framework and OpenAI GPT-4o-mini

**Quick start:**
```bash
cd my-ag-ui-cli-app
npm install
cp .env.example .env
# Edit .env and add your OpenAI API key
npm run dev
```

### Python Exploration

Python-based experiments with AG-UI protocol using uv package management.

## Purpose

This repository serves as a playground for:
- Testing AG-UI protocol implementation
- Exploring real-time agent interactions
- Experimenting with human-in-the-loop workflows
- Building AI-powered front-end applications