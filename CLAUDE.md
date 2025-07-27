# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is an experimental repository for exploring the AG-UI framework - an open protocol that standardizes how front-end applications connect to AI agents. The repository serves as a playground for:

- Testing AG-UI protocol implementation
- Exploring real-time agent interactions  
- Experimenting with human-in-the-loop workflows
- Building AI-powered front-end applications

## AG-UI Framework Context

AG-UI provides:
- Real-time interactivity with AI agents
- Live state streaming for dynamic updates
- Human-in-the-loop collaboration workflows
- Transport-agnostic communication (SSE, webhooks, WebSockets)
- Event-driven bidirectional communication
- Support for multiple agent frameworks (LangGraph, CrewAI, etc.)

The protocol focuses on the agent-user interaction layer, complementing A2A (agent-to-agent) and MCP (model context protocol).

## Development Environment

This project uses [uv](https://docs.astral.sh/uv/) for Python package management and virtual environment management.

### Requirements
- Python >=3.12 (as specified in pyproject.toml)
- uv package manager

### Common Commands

```bash
# Install dependencies and create virtual environment
uv sync

# Run Python scripts
uv run python script.py
uv run python hello.py  # Run the example script

# Add new dependencies
uv add package-name
uv add --dev package-name  # Development dependencies

# Run tests (when test framework is added)
uv run pytest

# Start Python REPL with project dependencies
uv run python
```

### Project Structure
- `pyproject.toml` - Project configuration and dependencies
- `uv.lock` - Locked dependency versions (created after first sync)
- `hello.py` - Example Python script

## Key Resources

- [AG-UI Documentation](http://docs.ag-ui.com/introduction) - Primary reference for framework capabilities and implementation guides
- Framework supports multiple agent backends and provides building blocks for human-agent communication

## Development Notes

Since this is an experimental/exploration repository, expect:
- Rapid prototyping and iteration
- Multiple implementation approaches being tested
- Focus on understanding AG-UI protocol mechanics
- Integration experiments with different agent frameworks

### Adding AG-UI Dependencies

When implementing AG-UI features, you'll likely need to add relevant packages:

```bash
# Example dependencies that might be needed
uv add fastapi uvicorn  # For web server/API
uv add websockets       # For WebSocket communication
uv add httpx           # For HTTP client requests
uv add pydantic        # For data validation
```